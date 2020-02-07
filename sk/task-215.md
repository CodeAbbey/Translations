<div class="centered">
<img alt="Game of Klotski - simple variant animation in 17 moves"
  src="https://codeabbey.github.io/data/klotski.gif"/>
<div class="hint">Animácia najjednoduchšieho  riešenia variácií v 17tich pohyboch<br/>
Cieľom je posunúť veľký červený obdĺžnik do stredu pravej strany.<br/>
Snáď pridáme interaktívne hry v javascripte neskôr...</div>
<br/><br/>
</div>

_Počiatočná myšlienka tejto úlohy s posúvaním blokov prišla od
[Radovana Markuša](https://www.codeabbey.com/index/user_profile/rajkoisawesome)
v [tomto](https://www.codeabbey.com/index/forum_topic/e8eb8d234cd33b35bcdb14e3ac02d3b1)
príspevku na fóre - vrelá vďaka!_

<p class="attention">Tento problém bol nedávno vytvorený a je v **testovacom móde**. Neváhajte ohlásiť chyby
ak myslíte, že ste nejaké našli, taktiež sa kľudne pýtajte na objasnenie alebo zlepšenie úlohy.</p>

Hra "Klotski" je evolúcia **15tich puzzle**: máme obdĺžnikové hracie pole s obdĺžnikovými dlaždicami,
ktoré sa vnútri posúvajú. Cieľom je posunúť jeden z blokov na určité miesto, ktoré je na protiľahlej strane.
[Viac v tomto článku na wiki](https://en.wikipedia.org/wiki/Klotski). Bez problémov túto hru nájdete pre platformy ako Windows, Linux
alebo Android (taktiež aj pre iné operačne systémy..) - alebo aj na webe - takže sa nehanbite si ju vyskúšať.

Herné pozície budú popísane latinskými písmenami: rovnaké písmeno je pre obdĺžniky jednej dlaždice.
Prázdne pozície sú označené bodkami. Tu sú dva príklady:

    ABBC        FDAI            ABBC        DAFC
    DBBE        FECI            ABBC        DAFC
    FGHI   =>   J..M            DEEF   =>   EEGH
    FJKI        GBBH            DGHF        JBB.
    L..M        LBBK            I..J        IBB.

V obidvoch je najväčšia `2x2` dlaždica (označované písmenom `"B"`) nazačiatku v strede na vrchu.
Úlohou je v obidvoch prípadoch posunúť ju do stredu na spodnej strane. Avšak, v prvom prípade (to isté,
je reprezentované v animácií uvedenej vyššie, aj keď je otočená o 90 stupňov po smere hodinových ručičiek) 
má 2 veľké (dvojité) dlaždice `2x1` a 10 jednotlivých `1x1` dlaždíc, tak je to jednoduché. Druhý prípad má 4 
jednotlivé (1x1) dlaždice a 5 dvojitých - a kvôli tomu ako sú otočené je úloha omnoho zložitejšia.

Očividne pre každý variant je "optimálne" riešenie - to, s najmenším počtom pohybov. Ako jeden pohyb počítame
jeden pohyb akéhokoľvek obdĺžnička, aj keď ho posunieme o viac ako 1 dlaždicu a aj keď posun nie je po rovnakej osi.
"Jednoduchý" variant by sa dal vyriešiť v `17` pohyboch, zatiaľ čo "ťažký" variant - v 81. Riešenie je obtiažne, no
nájdenie optimálneho riešenia môže byť ešte obtiažnejšie!

### Problémový výrok

V tejto úlohe sme dostali niekoľko verzií puzzle a potrebujeme určiť "dĺžku" (t.j. počet
pohybov) pre optimálne (najlepšie) riešenie.

**Vstupné dáta**

Prvý riadok obsahuje `N` - počet príkladov na otestovanie.  
Nasledujú samotné príklady, každý začína s popisom v riadku, ktorý poskytne veľkosť hracieho poľa (šírka x výška) a
úlohou (písmeno obdĺžnička a `X:Y` súradnice jeho pozície ľavého horného rohu vo finálnej pozícií).  
Napokon je samotné pole v nižšie uvedenom formáte.

**Výstupné dáta**

Iba `N` hodnôt, popisujúce počet pohybov pre optimálne riešenie pre každý príklad (oddelené medzerami).

Príklad:

	vstupné dáta:
	2
	field 4 by 5 ; move B to 1 : 3
	ABBC
	DBBE
	FGHI
	FJKI
	L..M
	field 5 by 4 ; move B to 3 : 1
	AADDI
	BBEG.
	BBEH.
	CCFFJ
	
	očakávana odpoveď:
	17 81

_prosím všimnite si formát popisujúcich riadkov - medzi každým prvkom sú medzery takže je jednoduchšie rozdeliť
a získať čísla..._

P.S. pre obdĺžničky ktoré majú výrez v ľavom hornom rohu je cieľová súradnica pre obdĺžniček najviac vľavo
v najvrchnejšom rade. Kvôli jednoduchosti sa však takýmto prípadom budeme vyhýbať.
