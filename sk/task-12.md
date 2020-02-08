Vysporiadanie sa so zvyškom môže niekedy sposobiť migrénu začínajúcim programátorom. Poďme napísať jednoduchý
program, aby sme si precvičili celočíselné delenie. Zároveň si vyskúšame aj prácu s dátumom,
ktorá niekedy spôsobuje bolesti hlavy aj skúseným programátorom.


V aritmetike, zvyšok (alebo modulo) je počet "ktorý ostal" po delení dvoch celý čísel
ktoré nedelia rovnako (z [Wikipédie][wiki]). Táto úloha poskytne ďalšie cvičenie s operáciou modulo.

[wiki]: https://cs.wikipedia.org/wiki/Zbytek_po_d%C4%9Blen%C3%AD

Predpokladajme, že máme dve časové informácie - napríklad, keď vlak alebo trajektová loď započnú svoju cestu a keď ju skončia.
Môže to vyzerať aj takto:

    začiatok: 3 Máj  17:08:30
	koniec  : 8 Máj  12:54:15

a nás zaujíma, koľko času (v dňoch, hodinách minútach a sekundách) zaberie takáto cesta (možno aby sme si vedeli
vybrať rýchlejší spôsob prepravy). Ako to môžeme vypočítať?

Jeden z najľahších spôsobov je:

- premeniť obidva časové údaje na veľké čísla, reprezentujúce sekundy od začiatku mesiaca (alebo roku či storočia);
- vypočítať ich rozdiel - t.j dĺžka cesty v sekundách;
- premeniť tento rozdiel naspäť na dni, hodiny, minúty a sekundy.

Pri prvom kroku by sme mohli vynásobiť minúty `60` a hodiny `60*60` atď. a nakoniec sčítaním všetkých čísel dohromady.
Tretí krok by mal byť vykonaný naopak, niekoľkými deleniami a s ukladaním zvyškov.

V tejto úlohe nám je poskytnutých niekoľko párov časových údajov. Predpokladáme, že obidva dátumy v páre sú
vždy v rovnakom mesiaci, takže bude poskytnutý iba počet dní. Chceme vypočítať rozdiel časových údajov pre každý pár.

**Vstupné dáta:** v prvom riadku bude počet príkladov, v ostatných riadkoch samotné príklady.  
Každý príklad obsahuje `8` čísel, `4` pre každý časový údaj: `deň1 hodina1 min1 sek1 deň2 hodina2 min2 sek2` (druhý
časový údaj bude vždy neskôr ako prvý).  
**Odpoveď:** pre každý príklad máte vypísať rozdiel nasledovným spôsobom `(dni hodiny minúty sekundy)` - prosím
všimnite si zátvorky - oddelené medzerami.

Príklad:

    vstupné dáta:
    3
	1 0 0 0 2 3 4 5
    5 3 23 22 24 4 20 45
    8 4 6 47 9 11 51 13
    
	odpoveď:
    (1 3 4 5) (19 0 57 23) (1 7 44 26)
