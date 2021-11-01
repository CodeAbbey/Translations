<!-- #Modulo und Zeitdifferenz -->
Der Umgang mit Resten kann Programmieranfängern große Kopfschmerzen bereiten. Lassen Sie uns ein einfaches Programm schreiben,
das diese Operation als Kernstück hat, um die Ganzzahldivision besser zu verstehen. Gleichzeitig üben wir damit auch den Umgang mit
Datumsübergaben - welche manchmal selbst erfahrenen Programmierern Kopfzerbrechen bereitet.


In der Arithmetik ist der Rest (oder Modulus) der "übrig gebliebene", ganzzahlige Betrag nach der Division von zwei Ganzzahlen,
welche sich nicht gleichmäßig teilen lassen (aus dem [Wiki][wiki]). Diese Aufgabe dient der weiteren Einführung der Modulo-Operationen.

[wiki]: http://en.wikipedia.org/wiki/Remainder

Angenommen, wir erhalten zwei Zeitstempel - zum Beispiel, wann ein Zug oder eine Fähre ihre Fahrt beginnt und wann diese endet. Das
kann wie folgt aussehen:

    Start: Mai 3, 17:08:30
    Ende:  Mai 8, 12:54:15

und wir sind neugierig darüber, wie viel Zeit (in Tagen, Stunden, Minuten und Sekunden) während der Reise vergeht (vielleicht, um
schnellere Möglichkeiten zu wählen). Wie können wir das herausfinden?

Einer der einfachsten Wege ist:

- beide Zeitstempel in große Zahlen umwandeln, welche die Sekunden vom Beginn des Monats (oder Jahres, oder Jahrhunderts) darstellen;
- die Differenz der beiden Zahlen berechnen - d.h. die Reisezeit in Sekunden;
- diese Differenz zurück in Tage, Stunden, Minuten und Sekunden umwandeln.

Die erste Operation könnte durchgeführt werden, in dem man die Minuten mit `60`, die Stunden mit `60*60` usw. multipliziert und all diese Werte addiert.
Im Gegensatz dazu sollte die Dritte Operation mithilfe mehrerer Divisionen unter Beibehaltung der Reste durchgeführt werden.

Bei dieser Aufgabe erhalten wir mehrere Paare von Zeitstempeln. Wir nehmen an, dass beide Daten des Paares im selben
Monat liegen und deshalb nur die Anzahl der Tage angegeben werden muss. Wir möchten die Differenz zwischen den Zeitstempeln von jedem Paar berechnen.

**Eingabe Daten:** enthalten in der ersten Zeile die Testfälle, die folgenden Zeilen enthalten die Testfälle selbst.  
Jeder Testfall enthält `8` Zahlen, `4` für jeden Zeitstempel: `tag1 stunde1 min1 sek1 tag2 stunde2 min2 sek2` (der zweite
Zeitstempel wird immer später als der erste sein).  
**Antwort:** für jeden Testfall sollen Sie die Differenz wie folgt ausgeben `(tage stunden minuten sekunden)` - bitte
beachten Sie auch die runden Klammern und trennen Sie ihre Antworten mit Leerzeichen.

Beispiel:

    Eingabe Daten:
    3
    1 0 0 0 2 3 4 5
    5 3 23 22 24 4 20 45
    8 4 6 47 9 11 51 13
    
    Antwort:
    (1 3 4 5) (19 0 57 23) (1 7 44 26)
