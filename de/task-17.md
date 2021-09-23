Prüsummen sind kleine Werte, die aus großen Datenmengen berechnet werden um zu testen, ob die Daten konsistent sind, d.h. ob sie
Fehler enthalten oder nicht.

Wenn Anna zum Beispiel eine Datei an Bob schickt, kann sie die Prüfsumme berechnen und sie Bob mitteilen. Bob kann die
Prüfsumme der empfangenen Datei ebenfalls berechnen und mit dem Wert von Anna abgleichen.

_Ein weiteres, deutlich häufigeres Beispiel - jede Bankkarte die Sie verwenden hat eine Prüfsumme in der letzten Ziffer, die dafür
sorgt, dass jedes Gerät verhindern kann, dass Sie versehentlich eine falsche Zahl eingeben (mehr dazu in der Übung zum
[Luhn Algorithmus](./luhn-algorithm))._

Bei der Programmierung von weiteren Aufgaben werden wir auf ähnliche Weise prüfen, ob das resultierende Array korrekt ist oder nicht. Um
Probleme mit solchen Aufgaben zu vermeiden möchten wir jetzt den Algorithmus zur Berechnung der Prüfsumme üben, um den es geht.

###Problemstellung

Sie erhalten ein Array, für das die Prüfsumme berechnet werden soll. Führen Sie die Berechnung wie folgt durch:
für jedes Element des Arrays (von Anfang an) addieren Sie das Element zur Variable `Ergebnis` und multiplizieren Sie diese Summe mit
`113` - dieser Wert soll modulo `10000007` gerechnet werden und der neue Wert der Variable `Ergebnis` sein, und so weiter.

Lesen Sie den [Artikel über Prüfsummen](../wiki/checksum) für eine detaillierte Beschreibung des Algorithmus.
Dort ist ebenfalls ein Berechnungsbeispiel zu finden.

**Eingabe Daten** enthalten in der ersten Zeile die Länge des Arrays.  
Die Array Werte selber folgen jeweils durch ein Leerzeichen getrennt in der zweiten Zeile.  
Die **Antwort** soll einen einzigen Wert enthalten - die berechnete Prüfsumm.

Beispiel:

    Eingabe Daten:
    6
    3 1 4 1 5 9
    
    Antwort:
    8921379

_Alle Eingabewerte liegen zwischen `0` und `1,000,000,000` - achten Sie daher auf einen möglichen Überlauf während
der Berechnungen!_
