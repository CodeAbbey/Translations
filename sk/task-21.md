Z tohto problému sa naučíme populárny programovací trik používaný v mnohých variantoch štatistických výpočtov.

Predstavte si, že nejaký horár chce spočítať borovice, jedle a brezy nejakej časti lesa. Môže ísť cez túto časť lesa
trikrát, pričom bude počítať iba borovice pri prvom prechode, jedle pri druhom a pri treťom iba brezy

Efektívnejší spôsob by bolo prejsť cez les iba raz a pre každý strom pridať jednu bodku do troch stránok v jeho
zošite - prvá strana pre borovice, ďalšia pre jedle a posledná pre brezy. To je myšlienka počítania podobných prvkov
v poradí pomocou poľa počítadiel (namiesto zošita).

Tu je pole s dĺžkou `M` s číslami od `1` po `N`, kde `N` je menšie alebo rovné  `20`.
Prejdeme cez pole, a spočítame koľkokrát sa tam každé číslo vyskytuje.
T.j niečo podobné ako úloha [počítanie samohlások](./vowel-count) , akurát potrebujeme viac ako jedno počítadlo.
Uistite sa, že máte samostatné pole, aby ste nevytvárali veľa oddelených premenných pre každé počítadlo.

**Vstupné dáta** obsahuje `M` a `N` v prvom riadku.  
Druhý (pomerne dlhší) riadok obsahuje hodnoty `M` oddelené medzerami.  
**Odpoveď** by mala obsahovať presne `N` hodnôt, oddelené medzerami. Prvá by mala byť počet `jednotiek`,
druhá počet - `dvojok` a tak ďalej.

Príklad:

	vstupné dáta:
	10 3
	3 2 1 2 3 1 1 1 1 3
	
	odpoveď:
	5 2 3
