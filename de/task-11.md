<!-- #Summe der Ziffern -->
Diese Programmieraufgabe ist dafür gedacht Sie in die Grundlagen des Zahlensystems einzuführen. Wir fangen an dieses
Konzept zu erlernen in dem wir mit dem Dezimalsystem spielen, welches wir täglich benutzen (bedenken Sie jedoch, dass der 
Computer es intern nicht verwendet - er konvertiert Zahlen nur in dieses System, wenn sie dem Benutzer angezeigt werden sollen).

Da jede Zahl die größer als 9 ist durch mehrere Ziffern dargestellt wird, können wir die Summe dieser Ziffern berechnen. Als Beispiel erhalten wir für die Zahlen `1492` und `1776`:

    1 + 4 + 9 + 2 = 16
    1 + 7 + 7 + 6 = 21

In dieser Aufgabe erhalten Sie mehrere Zahlen und sollen jeweils die Summe der Ziffern berechnen.  

**Wichtig:** obwohl viele Programmiersprachen über eingebaute Funktionen zur Umwandlung von Zahlen in Zeichenketten verfügen
(aus denen die Ziffern extrahiert werden können), sollten Sie diesen Ansatz nicht verfolgen (sofern Ihr Ziel das Erlernen einiger Programmiertricks ist).

**Stattdessen** sollten Sie einen Algorithmus implementieren, der mit wiederholter Division durch 10 (die Basis des Zahlensystems) und Aufsummierung der
Reste ein Ergebnis liefert. Lesen Sie den [Zahl zu Ziffern][numtodig] Artikel für weitere Details des Algorithmus.

[numtodig]: ../wiki/number-to-digits

###Problemstellung

**Eingabe Daten** haben folgendes Format:

- die erste Zeile enthält `N` - die Anzahl der zu verarbeitenden Werte;
- daraufhin werden `N` Zeilen folgen, in denen `3` Ganzzahlen `A B C` beschrieben werden, für die jeweils die Summe der Ziffern berechnet werden soll;
- für jeden Fall müssen Sie `A` mit `B` multiplizieren und `C` addieren (d.h. `A * B + C`) - daraufhin die Summe der Ziffern des Ergebnisses ermitteln.

Die **Antwort** sollte `N` Ergebnisse beinhalten, die durch ein Leerzeichen getrennt sind. Als Beispiel:

    Eingabe Daten:
	3
	11 9 1
	14 90 232
	111 15 111
	
	Antwort:
	1 16 21

Im ersten Fall muss `11*9+1 = 100` berechnet werden, die Summe der Ziffern ergibt sich durch `1+0+0 = 1`.
