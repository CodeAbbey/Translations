Wenn wir ein Programm schreiben das mit Fließkommazahlen handtiert ist es manchmal sinnvoll diese Zahlen auf 
eine Ganzzahl zu **runden**. Wir werden das auch für spätere Übungen brauchen um Lösungen zu vereinfachen.
Also lassen Sie uns hierfür in dieser kleinen Übung eineni Trick erlernen um das zu bewerkstelligen.

Gegeben sind mehrere Zahlen-Paare. Für jedes Paar dividieren Sie zunächst die erste Zahl mit der zweiten Zahl und geben 
dann das Resultat gerundet auf die **nächst nähere Ganzzahl** zurück. 

In Fällen wo das Resultat der Division genau `0.5` beträgt sollten Sie aufrunden (z.b. durch addieren von `0.5`).
Beachten Sie bitte, dass bei negativem Werten "größer" bedeutet das die Zahl "näher an der Null" liegt. 
Siehe Wikipedia Seite zum Thema [Rundung](https://de.wikipedia.org/wiki/Rundung) um mehr darüber zu erfahren. 

Wenn wir also von nun an in Zukunft bei  Übungsaufgaben von Rundung sprechen ist genau derselbe 
Algorythmus gemeint (es sei denn wir legen etwas anderes fest). 

**Eingabe Daten** beschreiben in der ersten Zeile die Anzahl der zu verarbeitenden Testfälle.  
In jeder nächsten Zeile steht jeweils ein Testfall als Zahlenpaar durch Leerzeichen getrennt.  
**Lösung** enthält das Resultat nach Division und Rundung für jedes Zahlenpaar, getrennt durch Leerzeichen. 

Beispiel:

    Eingabe Daten:
    3
    12 8
    11 -3
    400 5

    Lösung:
    2 -4 80

