Алгоритм применяется для подсчета числа уникальных элементов некоторого подмножества. Точный ответ может потребовать большой объем ресурсов, но на практике обычно достаточно приближенного значения с некоторой заранее заданной точностью.

Есть несколько особенностей алгоритма:
1. Точность оценки не снижается при увеличении размера множества
2. Потребляемая память постоянна. Она зависит от парамтера точности и сравнительно мала
3. Не требуется хранить элементы оцениваемого множества
4. Алгоритм работатет с потоком данных (последовательно получаетт и обрабатывает элементы из потока)
Обработка:
1. Получение элемента
2. Считаем хэш
3. Рассчитываем количество нулей, идущих подряд - ранг хэша

