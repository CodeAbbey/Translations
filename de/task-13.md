<!-- #Gewichtete Ziffernsumme -->
Dieses Programm ähnelt komplexeren Algorithmen zur Berechnung von CRC- oder anderen Prüfsummen und Hash-Funktionen für
Zeichenketten. Darüber hinaus wird es Ihnen weitere Übung für die Zerlegung von Werten in Dezimalstellen bieten. Vielleicht
möchten Sie vorher [Sum of Digits](./sum-of-digits--de) ausprobieren.

Berechnen wir die Summe der Ziffern wie bevor, aber multiplizieren diesesmal jede Ziffer mit Ihrer Position (von links zählend, beginnend
mit 1). Als Beispiel, wenn wir den Wert `1776` haben, kalkulieren wir die **gewichtete** Summe der Ziffern (nennen wir sie "wsd") wie folgt:

    wsd(1776) = 1 * 1 + 7 * 2 + 7 * 3 + 6 * 4 = 60

**Eingabe Daten** enthalten in der ersten Zeile die Anzahl der Testfälle.  
Darauf folgen in der zweiten Zeile die Werte selbst. Für jeden dieser Werte sollen Sie die gewichtete Summe der Ziffern berechnen.  
**Antwort:** wie üblich, geben Sie die Ergebnisse in einer Zeile und mit Leerzeichen getrennt aus.

Beispiel:

    Eingabe Daten:
    3
    9 15 1776
    
    Antwort:
    9 11 60
