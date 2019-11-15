<!-- #Average of an Array -->
Dôležité odvetvie matematiky, ktoré programovanie často používa je štatistika - t.j. výpočet charakteristiky
pre nejaké dáta. (Len pomyslite na štatistiky návštev / videnia webstránok atp.)
Učenie tejto brandže sa zvyčajne začína od zoznámenia sa s **priemernou hodnotou**.

Priemerná (v angličtine average) hodnota niektorých čísel, sa dá vypočítať ako súčet hodnôt vydelený množstvom. Napríklad:

    avg(2, 3, 7) = (2 + 3 + 7) / 3 = 4
	  avg(20, 10) = (20 + 10) / 2 = 15

Dostanete niekoľko polí, a vašou úlohou je pre každé z nich nájsť priemernú hodnotu.

**Vstupné dáta** v prvom riadku, poskytnú počet príkladov.      
Za nimi budú nasledovať samotné príklady, jeden na každý riadok. 
Každý príklad obsahuje polia s celými číslami a s hodnotou `0` označujúcu koniec. (Táto nula by nemala
byť zahrnutá vo výpočtoch!!!).  
**Odpoveď** by mala obsahovať priemernú hodnotu pre každé pole, zaokrúhlená k najbližšiemu celému číslu
(viz. [zaokrúhľovanie](./rounding)), oddelenú medzerami.

Príklad:

    vstupné dáta:
    3
    2 3 7 0
    20 10 0
    1 0
    
    odpoveď:
    4 15 1
