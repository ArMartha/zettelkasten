**Корневое дерево** — [дерево](Tree), в котором выделена одна вершина (корень дерева). Формально корневое дерево определяется как конечное множество ![T](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0) одного или более узлов со следующими свойствами:

1. существует один корень дерева ![T](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0);
2. остальные узлы (за исключением корня) распределены среди ![m\geq 0](https://wikimedia.org/api/rest_v1/media/math/render/svg/b0d2d765e4cfd7adfbca9ae0e37e75a2811c0333) непересекающихся множеств ![T_{1},...,T_{m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed7e6fdde555ab526b30398638aacb596d708c10), и каждое из множеств является корневым деревом; деревья ![T_{1},...,T_{m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed7e6fdde555ab526b30398638aacb596d708c10) называются поддеревьями данного корня  ![T](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0).
В корневом дереве каждый узел может иметь один родительский узел и может иметь любое количество дочерних узлов.

Здесь подразумевается иерархическая структура: у произвольного узла могут быт дочерние элементы и потомки под ним, а над ним могут быть родитель и предки.

При реализации корневых двоичных деревьев обычно поддерживаются только указатели на дочерние узлы, т.к. ко всем остальным узлам можно получить доступ через некоторый обход, начиная с корнем.

Иногда полезно сохранить указатели на листья дерева, но эти указатели труднее поддерживать, т.к. листья корневого дерева быстро меняются, когда мы вставляем элементы в дерево