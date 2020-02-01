Vyzerá to tak, že žiadny zo začiatočníckych programátorských kurzov nevynecháva precvičovanie [Euklidovského algoritmu](https://sk.wikipedia.org/wiki/Euklidov_algoritmus)
pre výpočet najväčšieho spoločného deliteľa dvoch čísel.

Najväčší spoločný deliteľ (v angličtine Greatest Common Divisor alebo `GCD`) čísel  `a` a `b`, je také celé číslo
`c`, ktorým je možné deliť  `a` aj `b` (bezo zvyšku) pričom je  `c` najväčšie možné číslo. Napríklad `gcd(20, 35) = 5` 
a `gcd(13, 28) = 1`. Euklidov algoritmus je celkom jednoduchý, budeme odčítať menšiu z hodnôt (`a` a `b`) od väčšej
a opakovať túto operáciu dokým sa hodnoty nebudú rovnať - táto posledná hodnota bude `gcd`. Pre urýchlenie procesu
môžeme namiesto odčítania použiť operáciu modulo.

Napríklad:

	20		35		- odčítame prvé od druhého
	20		15		- odčítame druhé od prvého
	5		15		- teraz odčítame prvé od druhého dvakrát
	5		5		- a tu je naše GCD

Najmenší spoločný násobok (v angličtine Least Common Multiple alebo `LCM`) čísel `a` a `b` je také celé číslo
`d`, ktoré je deliteľné obidvoma (a je najmenšie možné). Dá sa získať pomocou nasledujúceho pravidla:

	lcm(a, b) = a * b / gcd(a, b)

### Vaša úloha

**Vstupné dáta** obsahujú počet príkladov v prvom riadku.  
Na každom ďalšom riadku nasledujú príklady, ktoré obsahujú 2 čísla pre `A` a `B`.  
**Odpoveď** by mala obsahovať GCD a LCM pre každý pár v zátvorkách, oddelený medzerami napríklad takto:

    vstupné dáta:
	2
	2 3
	4 10
	
	odpoveď:
	(1 6) (2 20)
