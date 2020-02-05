<!-- #Lineárna funkcia -->
Veľmi bežný problém vo výpočtovom programovaní je určiť základný zákon, ktorými sa riadia niektoré javy.
Pre učebné účely si poďme vyskúšať jednoduchú úlohu -  objavovanie lineárnej závislosti dvoma uvedenými pozorovaniami
(napríklad, ako závisí cena produktu od rozmeru, váhy atď.)

Lineárna funkcia je definovaná vzťahom:

    y(x) = ax + b

Kde `a` a `b` sú nejaké konštanty.  
Napríklad, pre `a=3, b=2` má funkcia hodnoty `y = 2, 5, 8, 11...`  
kde `x = 0, 1, 2, 3...`

Vašou úlohou je určiť `a` a `b` dvoma bodmi, ktoré patria funkcií.  
T.j sú vám dané dva páry hodnôt `(x1, y1), (x2, y2)` pre ktoré funkcia platí
- a vy máte obnoviť samotnú funkciu.

**Vstupné dáta** má počet príkladov v prvom riadku
a potom samotné príklady v oddelených riadkoch. 
Každý riadok obsahuje `4` celé čísla (`x1 y1 x2 y2`).  
**Odpoveď** by mala byť tiež celé číslo, oddelená medzerami a samotné páry v zátvorkách, napríklad:

    vstupné dáta:
    2
    0 0 1 1
    1 0 0 1
    
    odpoveď:
    (1 0) (-1 1)
