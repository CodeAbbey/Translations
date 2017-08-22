Zufallszahlen werden in der Programmierung oft in der Spieleprogrammierung,Forschung, Cryptographie usw. eingesetzt, sind aber auch in Business-Anwendungen nützlich um z.B. eindeutige Benutzerkennungen, Passwörter oder ähnliches zu erzeugen.
Wir werden uns nun anschauen wie wir Zufallszahlen generieren können und mit einigen der einfacheren Methoden etwas üben.

Hier zeigen wir eine der älteren Methoden wie man Früher "vermeindliche" Zufallszahlen, d.h. eine Sequenz von anscheinend unabhängigen Zahlen erzeugt hat **(Pseudorandomisiert)**:

1. Wähle eine beliebige vierstellige Zahl als Startwert (Also zwischen `0000 ... 9999`).
2. Multipliziere sie mit sich selbst (Quadrieren, x^2) um eine 8 Stellige Zahl zu erhalten (Füge ggf. noch führende Nullen hinzu um die Zahl 8 Stellig darzustellen).
3. Schneide von der 8 Stelligen Zahl die ersten und letzten zwei Stellen ab (Truncate).
4. Die neue Zahl ist nun nur noch vierstellig und wird unser neuer Startwert für den nächsten Durchlauf zur Berechnung des nächsten Wertes. 
5. Um noch mehr Zahlen zu erhalten ab Schritt 2 wiederholen. 

Beispiel:

  5761                      - Das soll unsere Startnummer (Seed) sein.
	5761 * 5761 = 33189121    - quadrieren (x^2)
	33(1891)21 => 1891        - Vorne und Hinten 2 Ziffern abschneiden (truncate) und den mittleren Teil behalten
	
	1891                      - Das ist unser Resultat und zweite Nummer in der "Zufallsreihe".
	1891 * 1891 = 3575881     - Quadrieren (x^2) und Zahl mit führenden Nullen auffüllen um wieder eine 8 stellige Zahl zu erhalten
	03(5758)81 => 5758        - Vorne und Hinten 2 Ziffern abschneiden (truncate) und den mittleren Teil behalten
	
	5758                      - Das ist nun unsere dritte Nummer der "Zufallsreihe" (und so weiter und so fort...)

Es ist offensichtlich, dass sich die Reihe früher oder später in einer Endlosschleife wiederholen wird. Ein Beispiel:

	0001 -> 0000 -> 0000                   - Endlosschleife nach nur 2 Durchgängen
	4100 -> 8100 -> 6100 -> 2100 -> 4100   - Endlosschleife nach 4 Durchgängen

Für diese Übung erhalten Sie für mehrere Zahlenreihen immer eine bestimmte Start-Zahl (Seed). Sie sollen nun für jede Start-Zahl die Anzahl der Wiederholungen (Durchläufe) angeben bis sich eine Sequenz zu wiederholen beginnt. 

**Eingabe Daten:** Die erste Zeile enthält die Anzahl der Startwerte für welche Sie Zahlenreihen berechnen sollen. In der zweiten Zeile stehen die einzelnen Startwerte mit Leerzeichen getrennt hintereinander.  

**Lösung:** Die Lösung ist eine Leerzeichen separierte Zeile in der Sie die Anzahl der Durchläufe (Loops) angeben, bis sich die Zahlenreihe zu wiederholen beginnt. 

Beispiel:

	Eingabe Daten:
	3
	0001 4100 5761
	
	Lösung:
	2 4 88

*Ein Tip: Um die 8 Stellige Zahl zu zerschneiden teilen Sie sie durch `100` und dann nehmen Sie davon den "Rest" (Modulo, Remainder) der division mit `10000`.*
	
