<!-- #Максимум в Массиве -->
Эта задача - о популярном алгоритме "линейного поиска", который часто используется в составе более сложных алгоритмов
(например, сортировок).

Частой операцией над набором значений (например, массивом) является поиск наибольшего (или наименьшего) значения.
Для этого мы должны создать отдельную переменную - `текущий-максимум` (или минимум) - и проходя по массиву в цикле
сравнивать каждый из элементов с этой переменной. Если очередное значение оказывается больше `текущего`, то мы
копируем его в `текущий`, таким образом запоминая. В конце остаётся только вывести содержимое `текущего-максимума`.

Некоторые языки содержат готовые функции для поиска максимума/минимума в массиве, но конечно в методических целях
будет лучше если вы хоть раз реализуете этот несложный алгоритм самостоятельно. :)

**Входные данные** содержат ровно `300` целых чисел в одной строке.  
**Ответ** должен содержать максимум и минимум этих чисел, разделенные пробелом.

Пример:

    входные данные:
    1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2
    
    ответ:
    300 1
