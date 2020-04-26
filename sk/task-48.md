<!-- #Collatz Sequence -->
Toto je jeden z najzáhadnejších matematických problémov minulého storočia - pretože problémový výrok je mimoriadne jednoduchý
a pretože dôkaz je stále neznámy, avšak tento problém ponúka dobré programátorské cvičenie pre začiatočníkov.

**Predpokladajme**, že vyberieme nejaké počiatočné číslo `X` a potom vytvoríme sekvenciu hodnôt podľa pravidiel:

    if X je párne (t.j. X modulo 2 = 0) potom
	    buduceX = X / 2
	else
	    buduceX = 3 * X + 1

T.j ak `X` je nepárne, sekvencia rastie - a ak je párne, sekvencia klesá. Napríklad, pre `X = 15` dostaneme sekvenciu:

    15 46 23 70 35 106 53 160 80 40 20 10 5 16 8 4 2 1

Keď sekvencia dosiahne `1`, dostane sa do cyklu `1 4 2 1 4 2 1...`.

Háčik spočíva v tom, že akékoľvek počiatočné číslo `X` skôr či neskôr vyústi v spomínanú `1` - avšak aj keď táto
`Collatzova domienka` bola predstavená v roku `1937`, až do dnes nikto nenašiel dôkaz, že je tomu skutočne tak pre
akékoľvek `X` alebo, že existuje nejaký proti príklad (t.j číslo pre ktoré sekvencia nekončí `1` - buď nejakým väčším 
cyklom alebo nekonečným rastom).

**Vašou úlohou** je pre dané čísla, vypočítať koľko krokov je potrebných na dosiahnutie `1`.

**Vstupné dáta** obsahuje počet príkladov v prvom riadku.  
Druhý riadok obsahuje samotné príklady t.j hodnoty, pre ktoré by mali byť vykonané výpočty.
**Odpoveď** by mala obsahovať rovnaký počet výsledkov, pričom každý z nich je počet krokov potrebný pre 
dosiahnutie Collatzovej sekvencie na hodnotu `1`.

Napríklad:

    vstupné dáta:
	3
	2 15 97
	
	odpoveď:
	1 17 118
