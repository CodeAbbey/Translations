_Môže vam pomäcť ak vyriešite najskôr [Bubble in Array](./bubble-in-array) pred touto úlohou_

Triedenie polí je populárny problém pre nováčikov - a mimoriadne dôležitá vec v profesionálnom
programovaní (v databázach, knižniciach atď).

**Triedenie** je usporiadanie podľa nejakého jednoduchého pravidla založeného na porovnávaní. Napríklad máme dané pole:

    a = [3, 1, 4, 1, 5, 9, 2, 6]

a chceme aby jeho prvky boli usporiadané od najmenšieho po najväčšie - t.j. ak jeden prvok je pred (vľavo)
druhého - môžeme si byť istý že prvý prvok je buď menší alebo rovný ako ten druhý.

Matematicky, pre indexy `i` a `j` ak `i < j` potom `a[i] <= a[j]`.

**Bubble Sort** je jeden z najľahších metód pre takéto usporiadanie. Opíšeme to ešte jednoduchšie ako
zvyčajne:

1. Spravte `prechod` cez pole a, preskúmajte páry vedľajších prvkov (`N-1` párov pre pole z `N` prvkov).
2. Ak pre nejaký pár s indexom `i` a `i+1` neplatí podmienka `a[i] <= a[i+1]` , `vymeňte` tieto dva prvky.
3. Opakujte tento postup dovtedy, dokým nebude pole usporiadané.

Je očividné, ak `prechod` nevykoná žiadnu výmenu, pole je už zoradené a budúce `prechody` nič
nezmenia.

Existuje niekoľko spôsobov aby sme **vymenili** prvky s indexami `i` a `j`. Napríklad by sme mohli použiť dočasnú premennú `t`:

    t = a[i]
	a[i] = a[j]
	a[j] = t

###Problémový výrok

Vašou úlohou je implementovať popísanú verziu triedenia Bubble-Sort. Aby sme to otestovali skontrolujeme počet prechodov a počet
výmen predtým než pole vytriedime.

**Vstupné dáta** budú obsahovať rozmer poľa v prvom riadku a samotné pole v druhom riadku
(celé čisla oddelené medzerami).  
**Odpoveď** by mala obsahovať dve hodnoty - počet vykonaných prechodov a celkový počet výmen. Napríklad:

    vstupné dáta:
	8
	3 1 4 1 5 9 2 6
	
	odpoveď:
	5 8

Môžeme poznamenať, že počet výmen je približne úmerný `N^2` kde `N` je rozmer poľa (priemer je
asi `N^2 / 4`) takže čas potrebný na vykonanie algoritmu rastie značne rýchlejšie ako počet dát (preto
je takéto triedenie zriedka používané pre väčšie polia).

*Dodatočné informácie v angličtine môžete nájsť v téme na [porovnávanie triediacich aloritmov](../wiki/sorting-algorithms-comparison)*
