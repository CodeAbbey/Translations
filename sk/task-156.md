Účtovník opátstva, Brat Kyprian práve objavil škaredý problém! Treba zaplatiť malé odmeny dobrovoľníkom, ktorí
pracovali na farme počas leta, ale banka odmietla spracovať väčšinu platieb!

Čísla bankových kariet týchto pracovníkov boli napísané nedbalo a vyzerá to tak , že každé číslo obsahuje jednu z
dvoch chýb:

- buď sa niektoré číslice nedali rozpoznať;
- alebo niektoré dve čísla boli náhodou vymenené.

Avšak, Brat Kyprian našiel [článok na Wikipédií](https://cs.wikipedia.org/wiki/Luhn%C5%AFv_algoritmus) o algoritme,
ktorý sa používa na výpočet kontrolného súčtu čísel bankových kariet. Nižšie je uvedený súhrn tejto metódy.

###Algoritmus

Táto metóda je nazvaná po človeku menom **Hans Peter Luhn** ktorý ju navrhol. Hlavná myšlienka algoritmu je skontrolovať
najčastejšie typy chýb - a na druhej strane má byť jednoduchá, to znamená:

- zachovať jednoduchosť aby sa dala vypočítať s (alebo bez) pera a papiera, alebo s mechanickými zariadeniami;
- odhaliť chybu v jednej číslici;
- odhaliť neúmyselnú výmenu dvoch čísel.

Algoritmus sa vykonáva takto:

1. Sčítame všetky čísla od konca.
2. Avšak každá druhá číslica (`2.` od konca, `4.` od konca a tak ďalej) sa nesčítava "tak ako je" - namiesto toho
	je vynásobená dvomi (ak je výsledok dvojciferný - sčítajte jednotlivé číslice - alebo odčítajte od nich `9`).
3. Ak výsledok nie je násobok `10`, číslo je nesprávne.

Napríklad ak máme číslo `4123 1759 0498 1754` tak potom sčítame čísla takto (začíname od konca):

    4+(5*2-9)+7+(1*2) + 8+(9*2-9)+4+(0*2) + 9+(5*2-9)+7+(1*2) + 3+(2*2)+1+(4*2) = 70

Keďže `70` je deliteľná `10` tak potom je číslo pravdepodobne správne.

Na vytvorenie správneho čísla je posledná číslica skutočne iba **kontrolná číslica** - t.j. neukladá žiadne pracovné
informácie ale namiesto toho je zvolená tak, aby celé číslo dávalo správny kontrolný súčet.

---

###Problémový výrok

Prosím, pomôžte Bratovi Kyprianovi opraviť zoznam čísel bankových kariet. Niektorým chýba jedno číslo a vy máte toto
číslo obnoviť. Iné majú prehodené čísla vo dvojici - vašou úlohou je nájsť pár **najviac vľavo** ktorý,
ak vymeníte, bude tvoriť správne číslo karty.

Všetky čísla kariet budú `16` ciferné (toto je najbežnejšia dĺžka, dokonca aj v rozprávkach).

**Vstupné dáta** obsahujú zoznam pracovníkov, ktorí majú nesprávne čísla bankových kariet.  
Na každom ďalšom riadku sú samotné čísla kariet. Ak číslo obsahuje `"?"` (otáznik) namiesto nejakej číslice -
táto číslica by mala byť obnovená. Ak sú prítomné všetky čísla, potom by ste mali opraviť "chybnú výmenu".  
**Odpoveď** by mala obsahovať zoznam "opravených" čísel bankových kariet.

Príklad:

    vstupné dáta:
	4
	?942682966937054
	1217400151414995
	2146133934?67114
	2553514623364925
	
	odpoveď:
	3942682966937054 1217040151414995 2146133934667114 2553514623369425
