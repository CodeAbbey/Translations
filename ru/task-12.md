<!-- #Деление с остатком и разница во времени -->
Работа с остатками может причинять изрядную головную боль начинающим программистам. Напишем небольшую программу чтобы
получше изучить целочисленное деление. В то же время мы попрактикуемся в операциях с временными промежутками (которые могут
причинять головную боль даже опытным разработчикам).

В арифметике **остаток** это число "остающееся" после осуществления деления двух целых чисел, если они не делятся нацело.
Например `7` при целочисленном делении на `3` даёт частное `2` и остаток `1`.

Теперь представим что у нас есть два момента времени (две "временные метки") - например, когда паром отправляется и когда прибывает.
Они могут выглядеть как-то так:

    отправление: 3 Мая 17:08:30
    прибытие:    8 Мая 12:54:15

и мы хотим узнать, сколько времени (в днях, часах, минутах и секундах) уходит на путешествие (например чтобы выбрать
наиболее быстрый вариант). Как этого достичь?

Один из самых простых способов:

- преобразуем обе временных метки в большие числа, представляющие количество секунд истекших с начала месяца (или года, или столетия);
- посчитаем их разность - т.е. время путешествия в секундах;
- преобразуем эту разность обратно в дни, часы, минуты и секунды.

Первая операция осуществляется умножением минут на `60`, часов на `60*60` и т.п. с последующим сложением всех получившихся значений.  
Последняя же операция наоборот осуществляется последовательным делением и запоминанием остатков.

В этой задаче нам даны несколько пар временных меток. Допустим что обе даты в каждой паре принадлежат одному месяцу, так
что задаётся только день месяца. Требуется вычислить разность между метками каждой пары.

**Входные данные** - в первой строке указано количество тестов, а в остальных идут сами тесты, по одному в каждой.  
Каждый тест состоит из `8` чисел, по `4` для каждой из двух меток: `день1 час1 мин1 сек1 день2 час2 мин2 сек2` (вторая метка
всегда будет позже первой по времени).  
**Ответ** для каждого теста должен содержать разность в виде `(days hours minutes seconds)` - обратите внимание на скобки - с
пробелами между результатами.

Пример:

    входные данные:
    3
    1 0 0 0 2 3 4 5
    5 3 23 22 24 4 20 45
    8 4 6 47 9 11 51 13
    
    ответ:
    (1 3 4 5) (19 0 57 23) (1 7 44 26)
