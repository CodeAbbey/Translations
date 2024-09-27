<!-- #Triangoli -->
Un triangolo è un oggetto costituito da 3 segmenti di retta (lati del triangolo), collegati alle 
estremità.
La pagina [Wikipedia sui triangoli][wiki] fornisce una spiegazione più dettagliata.
Se abbiamo 3 segmenti di retta con lunghezze `A B C` - possiamo costruirci un triangolo (per esempio 
con le triplette `3 4 5` o `3 4 7` - anche se con area pari a zero) oppure scoprire che è impossibile 
costruirne uno (per esempio `1 2 4`).

[wiki]: http://it.wikipedia.org/wiki/Triangolo

Ti vengono fornite diverse triplette di valori che rappresentano le lunghezze dei lati dei triangoli.
Devi individuare tra quali di queste triplette è possibile costruire un triangolo e per quali non 
è possibile farlo.

**Dati di input:** La prima riga contiene il numero di triplette.
Le altre righe contengono le triplette (una per ciascuna riga).
**Risposta:** Devi restituire `1` o `0` per ciascuna tripletta(`1` se si pò costruire il
triangolo o altrimenti `0`).

Esempio:

    dati:
    2
    3 4 5
    1 2 4
    
    risposta:
    1 0