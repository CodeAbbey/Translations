<!-- #Collatz Sequence -->
Dies ist eines der rätselhaftesten mathematischen Probleme des letzten Jahrhunderts - sowohl, weil seine Aussage extrem einfach ist -
und weil der Beweis immer noch unbekannt ist. Wie auch immer, für Programmieranfänger bietet es eine sehr gute Übung.

**Angenommen** wir wählen einen Startwert `X` und bauen dann die Sequenz von Werten nach folgenden Regeln auf:

    wenn X gerade ist (d.h. X modulo 2 = 0) dann
        Xnext = X / 2
    ansonsten
        Xnext = 3 * X + 1

D.h. wenn `X` ungerade ist, wächst die Folge - und wenn sie gerade ist, nimmt die Folge ab. Zum Beispiel, mit `X = 15` haben wir folgende Sequenz:

    15 46 23 70 35 106 53 160 80 40 20 10 5 16 8 4 2 1
	
Nachdem die Fogle `1` erreicht hat, endet sie in der Schleife `1 4 2 1 4 2 1...`.

Der Clou liegt darin, dass jede beliebige Startzahl `X` die Sequenz erreicht, die früher oder später bei der `1` landet - allerdings
konnte, obwohl die `Collatz Vermutung` bereits `1937` formuliert wurde, bis heute niemand einen Beweis dafür finden, dass dies wirklich
für jede beliebige Startzahl `X` gilt, oder ein Gegenbeispiel finden(d.h. eine Zahl, deren Folge nicht mit `1` - sondern entweder in einer größeren Schleife endet oder unendlich groß wird).

**Ihre Aufgabe** ist es, für gegebene Zahlen zu berechnen, wieviele Schritte notwendig sind um zur `1` zu kommen.

Die **Eingabe Daten** enthalten in der ersten Zeile die Anzahl der Testfälle.  
Die zweite Zeile enthält die Testfälle - d.h. die Werte, für die die Berechnungen durchgeführt werden sollen.  
Die **Antwort** sollte die gleiche Anzahl an Ergebnissen enthalten, wobei jedes Ergebnis die Anzahl der Schritte ist, die benötigt werden um die Collatz Sequenz auf `1` zu bringen.

Als Beispiel:

    Eingabe Daten:
    3
    2 15 97

    Antwort:
    1 17 118
