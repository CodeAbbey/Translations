Wenn man Brett- oder Rollenspiele programmiert ist es manchmal nützlich mit Zufallszahlen zu arbeiten 
um z.b. einen Würfel zu emulieren. Programmieranfängern macht es jedoch oft einige Schwierigkeiten beim 
konvertieren von Zufallszahlen in die sechs Seiten eines Würfels (Würfel Punkte). 
Ziel dieser Übungsaufgabe ist es, einen Würfelwurf zu simulieren bei dem die Werte eines Zufallsgenerators
in eine Würfelpunktzahl gewandelt werden soll. 

Angenommen wir haben einen Zufallsgenerator, welcher uns zufällige Werte im Bereich zwischen
`0` (inklusive) bis `1` (exklusive)  liefert - dies kann man in Sprachen wie **Basic**, **Java**, **Matlab** usw. antreffen.

Wir möchten nun diese Fließkomma Werte in eine von sechs "Integer" Zahlen konvertieren: Von `1` bis `6`. 
Dies kann durch folgende Schritte erreicht werden:

1. Multiplizieren Sie die Zufallszahl mit N, welchen den gewünschten Spielraum des Generators festlegt.
    In unserem Fall multiplizieren wir mit `6` und erhalten somit eine FLießkommazahl zwischen 
    `0` (inklusive) bis `6` (exklusive)
2. Anschließend nehmen wir nur den Ganzzahl Wert (integer Teil, erhalten wir durch Verwendung von Funktionen 
    wie `floor` oder `int`) - Somit erhalten wir als Resultat nur einen der folgenden Beträge `0`, `1`, `2`, `3`, `4`, `5`
    mit einer gleichmäßigen Wahrscheinlichkeitsverteilung. 
3. Da wir jedoch Werte zwischen `1` bis `6` benötigen addieren wir einfach nur noch `1` zum Resultat. 

Sie erhalten nun mehrere Zufallswerte zwischen `[0 .. 1]`. (Welche durch einen Zugallsgenerator erzeugt werden.)
Konvertieren Sie diese Zufallswerte gemäß dem eben gezeigten Algorythus in ein Würfelergebnis. 

**Eingabe Daten:** Die erste Zeile enthält die Anzahl der zu konvertierenden Zufallswerte.  
Alle weiteren Zeilen enthalten jeweils einen zufälligen Fließkomma Wert, in der Form `0.142857`.  
**Lösung** enthält die in eine Würfel-Seite konvertierten Werte zwischen `1` bis `6` für jeden Eingabewert.

Beispiel:

    6
    0.59558786964
    0.861037873663
    0.385597702116
    0.246237673331
    0.808033385314
    0.0544673665427

    Lösung:
    4 6 3 2 5 1
