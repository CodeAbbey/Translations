<!-- #Triangles -->
Ein Dreieck ist ein Objekt, das aus drei Liniensegmenten (Seiten des Dreiecks) besteht, die durch ihre jeweiligen Enden verbunden sind.
Das [Wiki über Dreiecke][wiki] bietet eine ausführlichere Erklärung.  
Wenn wir drei Liniensegemente mit den Längen `A B C` haben - können wir damit entweder ein Dreieck bilden  
(zum Beispiel mit `3 4 5` oder `3 4 7` - allerdings mit dem Flächeninhalt 0) oder es ist unmöglich  
(zum Beispiel `1 2 4`).

[wiki]: https://de.wikipedia.org/wiki/Dreieck

Sie erhalten mehrere Tripel von Werten, die die Seitenlängen von Dreiecken darstellen.
Sie sollen dann entscheiden, aus welchen Tripel ein Dreieck gebildet werden kann und bei welchen nicht.

**Eingabe Daten:** Die erste Zeile enthält die Anzahl der Tripel.
Die folgenden Zeilen enthalten die Tripel selbst (jedes in einer eigenen Zeile).  
**Antwort:** Sie sollen für jedes Triplett `1` oder `0` ausgeben (`1` falls das Dreieck gebildet
werden kann und `0` falls nicht).

Beispiel:

    Daten:
    2
    3 4 5
    1 2 4
    
    Antwort:
    1 0
