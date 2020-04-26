Kontrolne súčty sú malé hodnoty vypočítané z veľkého množstva dát na otestovanie konzistencie dát, t.j. kontrola
chýb v dátach.

Napríklad ak Anna pošle nejaký súbor Bobovi, môže vypočítať kontrolný súčet a povedať ho Bobovi, a on
si vypočíta kontrolný súčet súboru, ktorý prijal a porovná to s hodnotami od Anny.

_Ďalší, ešte bežnejší príklad - všetky bankové karty, ktoré používate majú kontrolný súčet v poslednej číslici, 
takže zariadenia na kontrolu tohoto kontrolného súčtu, vám bránia použitiu nesprávnych čísel omylom (viac sa môžete
dočítať v cvičení [Luhnov Algoritmus](./luhn-algorithm--sk))._

Pre programovanie niekoľkých ďalších úloh použijeme podobný spôsob, aby sme skontrolovali či je výsledok polí (array) 
správny alebo nie. Aby sme predišli problémom s podobnými úlohami, poďme si teraz precvičiť algoritmus počítania kontrolných súčtov
a to je náš

###Problémový výrok

Dostanete pole pre ktoré vypočítate kontrolný súčet. Výpočet urobte nasledovne:
pre každý prvok poľa (od začiatku) pridajte tento prvok do premennej `výsledok` a vynásobte túto sumu číslom
`113` - táto nová hodnota, modulo `10000007` bude ďalšia hodnota `výsledku`, a tak ďalej.

Pre detailnejšie vysvetlenie si prečítajte [článok o kontrolnom súčte](../wiki/checksum).
Tam môžete nájsť aj príklad pre výpočty tejto kontrolnej sumy.

**Vstupné dáta** budú obsahovať dĺžku poľa v prvom riadku.  
Samotné hodnoty budú nasledovať v druhom riadku a budú oddelené medzerami.  
**Odpoveď** by mala obsahovať jednu hodnotu - vypočítaný kontrolný súčet.

Príklad:

    vstupné dáta:
	6
	3 1 4 1 5 9

	odpoveď:
	8921379

_Všetky vstupné hodnoty sú medzi `0` a `1,000,000,000` - uistite sa že nedôjde k presahu 
hodnôt počas výpočtov!_
