Diese Aufgabe führt Sie in das Thema "linearer Suchalgorythmus" ein, mit dem Sie sich gut vertraut machen sollten, 
da es sehr oft auch in komplexeren Programmieraufgaben wie "sortieren" benötigt wird. 

Eine häufige Verwendung ist z.B. das auffinden von "Extremen" wie maximal und minimal Werte in Zahlen-Reihen. 
Um dies zu erreichen müssen wir uns dieses mal die maximal und minimal Werte in einer separaten Variablen merken während
wir uns durch eine Zahlenreihe (Array) durcharbeiten um jedes Element damit zu vergleichen. 
Und wann immer ein Wert größer als unser gemerktes Maximum bzw kleiner als unser gemerktes Minimum ist speichern wir diesen Wert 
erneut in unseren temporären Variablen hierfür ab, als unser neues Maximum bzw Minimum. 

Am Ende eines Durchgangs erhalten wir so in den temporären Variablen die "Extrem Werte" einer Zahlenreihe.

**Eingabe Daten** enthalten dieses mal exakt `300` Zahlen in einer einzigen Zeile.  
**Lösung** soll nun die Maximum und Minimum Werte dieser Zeile, getrennt durch Leerzeichen enthalten.

Beispiel:

	Eingabe Daten:
	1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2
	
	Lösung:
	300 1
