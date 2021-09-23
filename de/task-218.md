_Vielen Dank an [Simon](https://www.codeabbey.com/index/user_profile/diehypotenuse), der die initiale Idee
dieses Problems hervor brachte, an [Graeme](https://www.codeabbey.com/index/user_profile/quandray) der feststellte,
dass die einfach Version des Problems zu einfach war :) und an [Alexandr](https://www.codeabbey.com/index/user_profile/aidsfrag) für die Hilfe beim korrigieren des Checkers._

Die [**Sintflut**](https://de.wikipedia.org/wiki/Sintflut) wird in verschiedenen religiösen und epischen
Quellen erwähnt. Der Regen war so stark, dass der Wasserspiegel anstieg und sogar die höchsten Gipfel bedeckte. Nachdem der Regen aufgehört
hatte und das Wasser verschwunden war, fanden sich die Überlebenden auf dem Gipfel des Berges Ararat (im heutigen Armenien) wieder.

Als Berg mit komplizierter Form aus Tälern und Spalten konnte an einigen tieferen Stellen etwas Wasser zurückbleiben, ähnlich wie 
bei Seen.

### Problemstellung

Wir haben eine ebene Karte des Berges als Höhenraster. Angenommen jede Gitterzelle ist eine Achtelmeile lang sowie breit und die Höhen 
sind ebenfalls in Achtelmeilen angegeben. Die Frage ist, wieviele Kubikachtelmeilen an Wasser zurückgehalten werden.

Eine formale Beschreibung davon, wie das Wasser vom Berg abfließt ist im Detail schwierig zu erstellen.
Es wird daher erwartet, dass man eine gewisse Intuition an den Tag legt um sich mit den folgenden Grundideen vertraut zu machen:

- Wasser fließt von höheren Zellen zu niedrigeren
- Wasser fließt nur in vier Richtungen, nicht diagonal
- keine Wassersäule oberhalb einer Zelle kann höher stehen als die Wasseroberfläche oder die Bodenoberkante einer der vier benachbarten Zellen 
- Wasser an den Randzellen des Gitters fließt vom Berg ab (in die umliegende Ebene)

**Eingabe** gibt in der ersten Zeile die Größe des Gitters an (eine einzige Zahl, da das Gitter quadratisch ist).  
Daraufhin folgt das Gitter selbst, `N` Zeilen mit `N` positiven Ganzzahlen.  
**Ausgabe** soll einen einzigen ganzzahligen Wert enthalten - die Wassermenge.

Beispiel:

	Eingabe Daten:
	6
	9 9 9 9 9 9
	9 6 5 1 3 9
	9 2 9 9 4 9
	3 4 9 9 7 9
	9 9 9 9 4 9
	9 9 9 9 5 9
	
	Antwort:
	14

Erklärung: unten dargestellt ist dasselbe Raster wie oben, mit den in Klammern gesetzten höhen der Wasseroberfläche:

	 9  9  9  9  9  9 
	 9  6 [6][6][6] 9 
	 9 [4] 9  9 [6] 9 
	 3  4  9  9  7  9 
	 9  9  9  9 [5] 9 
	 9  9  9  9  5  9 
