Keď hovoríme o **aritmetickej postupnosti** (alebo aritmetickej sekvencií), myslíme tým sériu
čísel s mimoriadnou vlastnosťou - každá hodnota je nasledovaná ďalšou, väčšou o predefinovanú
hodnotu (krok).

T.j. rozdiel `(K+1)` a `K`-tej hodnoty, je konštanta. Tu sú príklady postupností

	1 2 3 4 5 6 7 ...
	4 6 8 10 12 14 16...
	10 13 16 19 22 25 28...

Aritmetická postupnosť je úplne definovaná prvým členom (`A`) a prírastkovou
hodnotou - (`B`). Prvých pár členov by sme vyjadrili ako 

    A + (A + B) + (A + 2B) + (A + 3B) + ...

Vašou úlohou je vypočítať súčet prvých členov aritmetickej postupnosti.
[Stránka na wikipédií][wiki] o aritmetickej postupnosti by mohla značne pomôcť niekomu
kto vidí tento problém prvýkrát.

[wiki]: https://sk.wikipedia.org/wiki/Aritmetick%C3%A1_postupnos%C5%A5

**Vstupné dáta:** prvý riadok obsahuje počet skúšobných príkladov.  
Ďalšie riadky obsahujú samotné príklady vo forme trojíc hodnôt `A B N` kde `A` je prvá hodnota postupnosti,
`B` je prírastková hodnota a `N` je počet krokov postupnosti.  
**Odpoveď:** vašou úlohou je zobraziť výsledky (súčty prvých `N` členov) pre každú postupnosť, oddelenú medzerami.

Príklad:

    dáta:
    2
    5 2 3
    3 0 10
    
    odpoveď:
    21 30

_Vysvetlenie Príkladu. V prvom prípade máme postupnosť začínajúcu `5` a zvyšujúcu sa zakaždým o `2`.
K tomu chceme pričítať `3` prvky `5 + 7 + 9 = 21`. Druhý príklad je nenáročný. Začína s číslom `3` ale prírastok je `0`,
takže to je `3 + 3 + ... + 3 = 30` (celkovo `10` prvkov)._
