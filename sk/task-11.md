<!-- #Sum of digits -->
Toto cvičenie je určené na úvod základov číselného(decimálneho) systému. Začneme sa učit
tento koncept hraním sa s decimálnym systémom, ktorý používame každý deň (aj keď by ste mali mať na pamäti, že počítač
tento systém nepoužíva, používa binárny systém, - a decimálne čísla konvertuje v momente keď majú byť zobrazené užívateľovi).

Každé číslo väčšie ako 9 je reprezentované niekoľkými číslicami, takže môžme spraviť súčet týchto čísel. Napríklad,
pre čísla `1492` a `1776` dostaneme:

    1 + 4 + 9 + 2 = 16
	1 + 7 + 7 + 6 = 21

V tejto úlohe dostanete niekoľko čísel a vašou úlohou je vypočítať súčet ich jednotlivých číslic.  

**Dôležité:** zatiaľ čo mnohé programovacie jazyky majú vstavané funkcie na konverziu čísel na reťazece
(z ktorých môžu byť čísla extrahované), nemali by ste ich používať (pretože vašim cieľom je naučiť sa nejaké tie programátorske triky).

**Namiesto toho** potrebujete implementovať algoritmus s opakovaným delením 10 (základ číselneho systému) 
a sčítavaním zvyškov. Prečítajte si článok [číslo na číslice][numtodig] pre detaily algoritmu.

[numtodig]: ../wiki/number-to-digits

###Problémový výrok

**Vstupné dáta** sú v nasledujúcom formáte:

- prvý riadok obsahuje `N` - počet hodnôt na spracovanie;
- a potom nasleduje `N` riadkov popisujúce hodnoty, pre ktoré by mal byť vypočítaný súčet číslic  `3` celými číslami `A B C`;
- pre každý príklad potrebujete vynásobiť `A`čko s `B`čkom a pripočítať `C`éčko (t.j. `A * B + C`) - a potom vypočítať súčet čísel výsledku.

**Odpoveď** by mala mať `N` výsledkov, taktiež oddelená medzerami. Napríklad:

    vstupné dáta:
	3
	11 9 1
	14 90 232
	111 15 111
	
	odpoveď:
	1 16 21

V prvom príklaďe je potrebné vypočítať `11*9+1 = 100` a súčet jeho číslic je `1+0+0 = 1`.

_translated by [Radovan Markus](https://www.codeabbey.com/index/user_profile/rajkoisawesome)_
