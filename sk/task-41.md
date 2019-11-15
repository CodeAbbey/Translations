<!-- #Median of Three -->

Vyriešili ste už problém [Minimum of Three](./min-of-three) - a nebola to pre vás dostatočná výzva? Keďže programátori
by si mali zlepšovať logické myslenie (a nie iba zručnosti v programovacom jazyku), zmeňme úlohu aby bola
obtiažnejšia.

Opäť dostanete trojicu čísel, ale teraz musíte zvoliť prostrednú hotnodu - t.j. nie najvyššiu ani najnižšiu.
Takéto číslo nazývame **Stredná hodnota** (v angličtine **Median**) množiny, pola atď. 

Uisťujeme vás, že tento problém nie je "ďalšia sprostá úloha" - ale používa sa napríklad ako časť vo výkonných triediacich 
algorimoch.

**Vstupné dáta** v prvom riadku obsahujú počet trojíc na spracovanie.  
Každý ďalší riadok obsahuje samotnú trojicu čísel.   
**Odpoveď** by mala obsahovať vybrané stredné hodnoty, oddelené medzerami.

Príklad:

    dáta:
    3
    7 3 5
    15 20 40
    300 550 137
	
	odpoveď:
	5 20 300

Poznámka: ak váš program bude obsahovať priveľa  if-else-if-else výrokov, tak potom robíte pravdepodobne niečo nesprávne.
Jednoduché riešenie by nemalo obsahovať viac ako 3 if-else výroky.
