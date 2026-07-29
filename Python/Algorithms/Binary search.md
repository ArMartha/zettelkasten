#algorithm #search
A classical search algorithm in *sorting* array which use divide and conquer strategy.  
Base for binary search tree and B-tree data structures.
Binary search uses in sorted array
Worth-case performance: O(n)

Бинарный поиск находит элемент в отсортированном массиве за O(log n), сравнивая с серединой и отбрасывая половину на каждом шаге. Классическая деталь: долгое время в стандартных библиотеках (включая Java) содержалась ошибка переполнения при вычислении середины через `(low + high) / 2` — при больших массивах сумма могла превысить диапазон int. Правильная формула: `low + (high - low) / 2`.

Example on Python/Go:
