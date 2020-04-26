<!-- #Triangles -->
Trojuholník je objekt zložený z troch segmentov (strán), spojený koncami.
[Wikipédia][wiki] poskytne detailnejšie vysvetlenie.  
Ak máme tri riadky segmentov s dĺžkami `A B C` - tak buď môžeme s nimi poskladať trojuholník  
(napríklad s `3 4 5` alebo `3 4 7` - aj keď tento je s nulovým obsahom) alebo je to nemožné  
(napríklad `1 2 4`).

[wiki]: https://sk.wikipedia.org/wiki/Trojuholn%C3%ADk

Poskytnutých je niekoľko trojíc hodnôt reprezentujúce dĺžku strán trojuholníka.
Vašou úlohou je rozhodnúť o tom či sa z trojice hodnôt dá poskladať trojuholník alebo nie.

**Vstupné dáta:** Prvý riadok obsahuje počet trojíc.  
Ďalšie riadky obsahujú samotné trojíc (jedna trojica na každý riadok).  
**Odpoveď:** Bude `1` alebo `0` pre každú trojicu (`1` ak sa trojuholník
dá poskladať a `0` ak nie).

Príklad:

    dáta:
    2
    3 4 5
    1 2 4
    
    odpoveď:
    1 0
