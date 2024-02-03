**Дерево** — это [связный]([[LinkedGraph]]) [ациклический граф]. Связность означает наличие маршрута между любой парой вершин, ацикличность — отсутствие циклов. 
Дерево определяется как [[Graph]] без каких-либо неориентированных циклов (т.е. циклов, которые возникли бы, если бы мы заменили ориентированные ребра на неориентированные ребра) или каких-либо несвязанных частей. Отсюда, в частности, следует, что число рёбер в дереве на единицу меньше числа вершин, а между любыми парами вершин имеется один и только один путь.

Есть несколько граничных случаев:
- дерево без узлов является допустимым деревом, называемым «пустым» деревом
- дерево с одним узлом (и без ребер) также является допустимым деревом

Реализация деревьев осуществляется через указатели на дочерние узлы