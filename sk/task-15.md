Tento problém uvádza populárny algoritmus "lineárneho vyhľadávania", ktorý by ste sa mali dôkladne naučiť 
pretože je často používaný v programovaní komplexnejších úloh (zoraďovanie atď.)

Veľmi bežná operácia na sled hodnôt alebo polí je nájsť krajné hodnoty - maximálne alebo minimálne. Aby sme toto 
docielili potrebujeme uložiť **aktuálnu maximálnu** (alebo minimálnu) hodnotu v oddelených premenných, a potom 
prejsť cez pole, porovnávať každý z elementov s touto hodnotou. Kedykoľvek je nasledujúca hodnota väčšia ako táto
dočasná premenná, táto nová hodnota by mala byť do nej skopírovaná (ako nové maximum).

Na konci tohoto prechodu táto dočasná premenná bude obsahovať krajnú hodnotu.

**Vstupné dáta** vám poskytnú presne `300` čísel v jednom riadku.  
**Odpoveď** by mala obsahovať maximálnu a minimálnu hodnotu z týchto čísel oddelenú medzerou.

Príklad:

	vstupné dáta:
	1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2
	
	odpoveď:
	300 1

_translated by [Radovan Markus](https://www.codeabbey.com/index/user_profile/rajkoisawesome)_
