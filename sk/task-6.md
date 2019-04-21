Keď sa program vysporiadava s číslami, ktoré majú desatinú časť, niekedy chceme takéto hodnoty **zaokrúhliť** na celé čísla.
Toto budeme potrebovať na programovanie niektorých neskorších problémov (na zjednodušovanie odpovedí, napríklad), takže sa
poďme naučiť tento trik s nasledujúcou úlohou.

Máme tu niekoľko párov čísel. Pre každý pár najprv vydelíte prvé číslo druhým a výsledok
bude zaokrúhlený **na najbližšie** celé číslo.

V prípadoch, keď výsledok obsahuje na mieste desatiného čísla presne `0.5` hodnota by mala byť zaokrúhlena nahor.
(t.j. ďalším pridaním `0.5`). Všimnite si, že pre záporne hodnoty "väčšie" znamená
"bližšie k nule". Viac na článku [Zaokrúhľovanie](https://cs.wikipedia.org/wiki/Zaokrouhlen%C3%AD)
pre presnejšie vysvetlenia.

V každých ďalších problémoch, kde je spomenuté zaokrúhľovanie - sa predpokladá použitie
tohoto istého algoritmu (pokiaľ nie je inak špecifikované).

**Vstupné dáta** v prvom riadku je počet skúšobných príkladov.  
Ďalšie riadky budú obsahovať jeden skúšobný príklad (t.j. číselný pár) pre každý riadok.  
**Odpoveď** by mala obsahovať delenie a zaokrúhlenie výsledku pre každý pár oddelený medzerami.

Príklad:

	vstupné dáta:
	3
	12 8
	11 -3
	400 5
	
	odpoveď:
	2 -4 80

_translated by [Radovan Markus](https://www.codeabbey.com/index/user_profile/rajkoisawesome)_
