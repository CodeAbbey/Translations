<!-- #Hod Kockou  -->
Pri programovaní RPG alebo stolových hrách, veľa začínajúcich programátorov okúsi problémy v konverzií náhodných hodnôt
na jednotlivé čísla pri hode kockou. Cieľom tejto úlohy je vyskúšať si simuláciu hodom kocky, hodnotami z generátoru
náhodných čísel.

Predpokladajme, že máme generátor, ktorý nám da hodnoty v rozmedzí od  `0` (je v intervale) do `1` (nie je v intervale)
s týmto sa môžete stretnúť v jazykoch ako **Basic**, **Java**, **Matlab** atď.

Chceme konvertovať tieto hodnoty s rôznou dĺžkou desatinného rozvoja na 6 **celých** čísel: od `1` do `6`. Toto sa dá
dosiahnuť nasledovne:

1. Vynásobením náhodnej hodnoty číslom N, čo je počet odlišných hodnôt, ktoré chceme získať - v našom prípade 
    násobíme `6` a výsledok bude číslo s rôznou dĺžkou desatinného rozvoja od `0` (je v intervale) do `6` (nie je v intervale)
2. Teraz vezmeme celočíselnú časť tohoto výsledku (funkciou ako `floor` alebo konverziou na `int`) - hodnota
    sa teraz stane jedným z čísel `0`, `1`, `2`, `3`, `4`, `5` .
3. Keďže my chceme hodnoty od `1` do `6` jednoducho pripočítame `1` k nášmu výsledku. 

Teraz dostanete niekoľko čísel v rozmedzí `[0 .. 1)` (uisťujeme vás, že sú poskytnuté generátorom náhodných čísel) - 
a vašou úlohou je premeniť ich na čísla kocky aplikovaním vyššie zmieneného algoritmu.

**Vstupné dáta** budú obsahovať počet hodnôt na premenu v prvom riadku.
Ostatné riadky budú obsahovať samotné hodnoty, čísla ako `0.142857`. 
**Odpoveď** by mala obsahovať čísla od `1` do `6` pre každú hodnotu, vytvorené zmieneným algoritmom.

Príklad:

    6
	0.59558786964
	0.861037873663
	0.385597702116
	0.246237673331
	0.808033385314
	0.0544673665427
	
	odpoveď:
	4 6 3 2 5 1
