<!-- #Контрольная Сумма Массива -->
Контрольные суммы (чексуммы) - это небольшие значения вычисляемые по сравнительно большим объёмам данных, чтобы убедиться
в их консистентности - т.е. чтобы определить что данные не были случайно повреждены, изменены, частично утрачены.

Например если Анна посылает файл Бобу, она может вычислить его чексумму и сообщить её Бобу. Он
также посчитает сумму по полученному файлу и сможет понять, принял ли он файл целиком или, быть может, потерял
кусок из-за обрыва связи (а может его подредактировала коварная Ева?).

_Другой популярный пример - все банковские карты (в т.ч. те которые вы наверняка используете)
содержат контрольную сумму в последней цифре номера, на тот случай если вы набирая этот номер случайно
поменяете пару цифр местами или наберете какую-то одну неверно. (вы можете узнать об этом подробнее из задачи
[Luhn Algorithm](./luhn-algorithm))._

Для работы с несколькими следующими задачами нам понадобится подобный способ определения корректности полученного
массива. Поэтому попрактикуемся сейчас с соответствующим алгоритмом чтобы избежать ошибок в дальнейшем.

###Условие задачи

Нам дан массив для которого нужно посчитать контрольную сумму. Делается это следующим образом: каждый элемент
(начиная с первого) добавляем к текущему результату и умножаем то что получилось на `113` -
то что получилось берем по модулю `10000007` - оно и будет новым значением результата, и так далее.

[Статья о контрольной сумме](../wiki/checksum) содержит пример таких вычислений.

**Входные данные** содержат длину массива в первой строке.  
Значения массива следуют во второй строке, через пробел.  
**Ответ** должен содержать единственное число - получившуюся чексумму.

Пример:

    входные данные:
    6
    3 1 4 1 5 9
    
    ответ:
    8921379

_Все значения массива будут в диапазоне от `0` до `1 000 000 000` -
не забудьте принять меры против возможного переполнения промежуточного результата!_
