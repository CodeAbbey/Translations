Ein wichtiger Zweig der Mathematik, welcher sich stark auf die Programmierung stützt, ist die Statistik - d.h. die Berechnung von Merkmalen
für bestimmte Daten. (Man denke nur an die Statistik von Besuchern / Aufrufe einer Website usw.)
Das Erlernen dieser Disziplin beginnt in der Regel mit dem Kennenlernen eines **Durchschnittswerts**.

Der Durchschnitt (oder Mittelwert) einiger Zahlen kann als ihre Summe geteilt durch die Anzahl der Zahlen berechnet werden. Als Beispiel:

    avg(2, 3, 7) = (2 + 3 + 7) / 3 = 4
    avg(20, 10) = (20 + 10) / 2 = 15

Sie erhalten mehrere Arrays, für die Sie jeweils den Durchschnittswert ermitteln sollen.

Die **Eingabe Daten** enthalten die Anzahl der Testfälle in der ersten Zeile.  
Daraufhin folgen die Testfälle selbst, einer pro Zeile.  
Jeder Testfall beinhaltet ein Array mit positiven Ganzzahlen, der Wert `0` markiert jeweils das Ende eines Arrays. (diese Null soll nicht
bei der Berechnung mit einbezogen werden!!!).  
Die **Antwort** sollte den Durchschnittswert für jedes einzelne Array enthalten, gerundet auf die nächste Ganzzahl (siehe [task on rounding](./rounding)), und mit einem Leerzeichen getrennt.

Beispiel:

    Eingabe Daten:
    3
    2 3 7 0
    20 10 0
    1 0
    
    Antwort:
    4 15 1
