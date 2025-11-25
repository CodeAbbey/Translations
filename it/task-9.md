<!-- #Triangoli -->
Un triangolo è un oggetto costituito da tre segmenti (lati del triangolo), collegati da estremità.
[Wiki sui triangoli][wiki] fornisce una spiegazione più dettagliata.
Se abbiamo tre segmenti di lunghezza `A B C`, possiamo costruire un triangolo con essi
(ad esempio con `3 4 5` o `3 4 7`, sebbene questo abbia area zero) oppure lo troviamo impossibile
(ad esempio `1 2 4`).

[wiki]: http://en.wikipedia.org/wiki/Triangle

Ti vengono fornite diverse terne di valori che rappresentano le lunghezze dei lati dei triangoli.
Dovresti dire da quali terne è possibile costruire un triangolo e da quali no.

**Dati di input:** La prima riga conterrà il numero di terzine.
Le altre righe conterranno le terzine stesse (ciascuna su una riga separata).
**Risposta:** Dovresti restituire `1` o `0` per ogni terzina (`1` se il triangolo può essere
costruito e `0` altrimenti).

Esempio:

    dati:
    2
    3 4 5
    1 2 4
    
    risposte:
    1 0
