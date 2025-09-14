Uses AES instructions for fast-hashing and performs key lookups in parallel using [[SSE instructions]].
SwissMap is faster and more memory efficient than Golang's built-in map.

"Flat" Swiss tables store their value_type inside the container's main array to avoid memory indirections. Because they move data when they rehash, elements do not get pointer stability. 
The "node" Swiss table allocate their value_type in nodes outside of the main array. Because of the separate allocation, they provide pointer stability. As  well, the stored data and empty slots only require 8 bytes.

Underlying hash algorithm can be changed without modifying user code, which allows us to improve both it and types.

Swiss tables have a denser, more cache-friendly memory layout and utilize SSE instructions to accelerate key-value lookups.
Swiss Table design was a perfect fit for our chunk index use-case.
Primary difference between the built-in map and SwissMap is their hashing system. The built-in map uses an "open-hashing" scheme where key-value pairs with colliding hashes are collected into a single "bucket". To look up a value in the map, you first choose a bucket based on the hash of the key, and then iterate through each key-value pair in the bucket until you find a matching key.

A  key optimization is the use of "extra hash bits" that allow for fast equality checking while iterating through slots of a bucket. Before directly comparing the query key with a candidate, the lookup algorithm first compares an 8-bit hash of each key (independent from the bucket hash) to see if a positive match is possible. This fast pre-check has a false-positive rate of 1/256 and greatly accelerates the searches through a hash table bucket.

Swiss table uses a different hashing scheme called "closed-hashing". Rather than collect elements into buckets, each key-value pair in the hash-table is assigned its own ""slot". The location of this slot is determined by a probing algorithm whose starting point is determined by the hash of the key. The simplest example is a linear probing search which starts at slot  ```
```go 
hash(key) mod size
````
and stops when the desired key is found, or when an empty slot is reached. This probing method is used both to find existing keys and to kind insert locations for new keys. SwissTables uses "short hashes" to accelerate equality checks during probing. However, unlike the built-in map, its hash metadata is stored separately from the key-value data.
The segmented memory layout of SwissTable is a key driver of its performance. Probe sequences through the table only access the metadata array until a short hash match is found. This access pattern maximizes cache-locality during probing. Once a metadata match is found, the corresponding keys will almost always match as well. Having a dedicated metadata array also means we can use SSE instructions to compare 16 short hashes in parallel. Using SSE instructions is not only faster, but is the reason SwissTable supports a maximum load factor of 14/16. The observation is that "negative" probes (searching for a key that is absent from the table) are only terminated when an empty slot is encountered. The fewer empty slots in a table, the longer the average probe sequence takes to find them. In order to maintain O(1) access time for our hash table, the average probe sequence must be bounded by a small, constant factor. Using SSE instructions effectively allows us to divide the length of average probe sequence by 16.