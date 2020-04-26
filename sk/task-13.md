Tento program sa podobá na komplexnejšie algoritmy pre výpočet CRC a iných kontrolných súčtov a tiež hash-funkcií na
písmena reťazcov. Okrem toho vám poskytne ďalšie cvičenie pre rozdeľovanie hodnôt na čísla. Pred touto úlohou
by ste možno chceli skúsiť najprv [Sum of Digits.](./sum-of-digits)

Poďme vypočítať ciferný súčet, tak ako predtým, ale násobením každej číslice jej pozíciou (počítaním zľava, začneme
od 1). Napríklad, pre hodnotu `1776` spočítame  **vážený** ciferný súčet (túto funkciu nazveme "wsd") pre:

	wsd(1776) = 1 * 1 + 7 * 2 + 7 * 3 + 6 * 4 = 60

**Vstupné dáta** bude počet príkladov v prvom riadku.  
Samotné hodnoty sú v druhom riadku. Vašou úlohou je
vypočítať vážený ciferný súčet pre každú hodnotu.  
**Odpoveď:** ako zvyčajne, výsledky oddelené medzerami vypíšte do riadku.

Príklad:

    vstupné dáta:
    3
    9 15 1776
    
    odpoveď:
    9 11 60
