Wenn wir über **arithmetische Progression** (oder arithmetische Folgen) sprechen, meinen wir die Serie
von Zahlen mit einer besonderen Eigenschaft - auf jeden Wert folgt ein weiterer, der um einen vordefinierten Betrag (Schritt)
größer ist.

D.h. die Differenz des `(K+1)`-ten und `K`-ten Wertes ist eine Konstante. Hier sind Beispiele für solche Sequenzen

	1 2 3 4 5 6 7 ...
	4 6 8 10 12 14 16...
	10 13 16 19 22 25 28...

Somit ist die arithmetische Sequenz druch das erste Glied (`A`) und den Inkrement
Wert - die Schrittweite - (`B`) vollständig definiert. Die ersten Werte der Sequenz können wie folgt ausgedrückt werden

    A + (A + B) + (A + 2B) + (A + 3B) + ...

Sie sollen die Summe der ersten Glieder der arithmetischen Folge berechnen.
Die [Wikipedia Seite][wiki] über arithmetische Progression könnte für jemanden der ihnen zum ersten mal begegnet
eine gute Hilfe sein.

[wiki]: https://de.wikipedia.org/wiki/Arithmetische_Folge

**Eingabe Daten:** haben in der ersten Zeile die Anzahl der Testfälle.  
Die folgenden Zeilen enthalten Wertetripel der Form `A B N` bei denen `A` der erste Wert der Sequenz ist,
`B` die Schrittweite und `N` die Anzahl der ersten Werte die erzeugt werden sollen.  
**Antwort:** Sie sollen die Ergebnisse (also die Summe der ersten `N` Sequenzglieder) für jede Sequenz durch Leerzeichen getrennt ausgeben.

Beispiel:

    Eingabe Daten:
    2
    5 2 3
    3 0 10
    
    Antwort:
    21 30

_Erklärung des Beispiels. Im ersten Fall haben wir eine Sequenz mit dem Startwert `5` und dem Inkrement (der Schrittweite) `2`.
Wir summieren die ersten `3` Elemente der Sequenz `5 + 7 + 9 = 21`. Der zweite Fall ist einfacher. Er startet mit `3`, aber das Inkrement ist `0`,
also ist die Summe `3 + 3 + ... + 3 = 30` (insgesamt für `10` Elemente)._
