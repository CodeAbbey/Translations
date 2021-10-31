<!-- #Fahrenheit zu Celsius -->
Diese Programmierübung ist ähnlich zur Aufgabe "Summieren in Schleife" ("counting sums in loop"), 
bedarf aber ein wenig mehr Berechnungen


<div class="text-center">
	<img alt="fahrenheit und celsius" src="https://codeabbey.github.io/data/fahrenheit_celsius.png"/>
	<div class="hint">Anmerkung: Die Übung <a href="./rounding--de">Rundung</a> erklärt den Rundungs-Algorythmus
	den wir in dieser Aufgabe nun wieder benutzen werden.</div>
</div>

Zur Messung von Temperaturen gibt es zwei weitverbreitete Systeme - Celsius and Fahrenheit.
Das erste ist in Europa und weltweit weit verbreitet, während das zweite vor allem in britisch geprägten
Gebieten wie den USA zu finden ist. 

Auf der Celsius-Skala friert Wasser bei genau 0 Grad C und kocht bei 100 Grad C. Auf der Fahrenheit-Skala
friert Wasser bei 32 Grad F und kocht bei 212 Grad F. Mehr darüber können Sie im Wikipedia Beitrag 
[Grad Fahrenheit](https://de.wikipedia.org/wiki/Grad_Fahrenheit) nachlesen. 

Verwenden Sie diese Punkte für ihre Umrechnung von Temperaturen. 


Die Aufgabe besteht nun darin, ein Programm zu schreiben, welches Fahrenheit in Celsius umrechnen kann. 

**Eingabe Daten** enthalten `N+1` Werte, der erste davon ist `N` selbst. (**Beachten Sie**, dass Sie diesen nicht konvertieren).  
**Lösung** enthält genau `N` Resultate, gerundet auf die nächstnähere Ganzzahl und durch Leerzeichen getrennt. 

Beispiel:

    Eingabe Daten:
    5 495 353 168 -39 22

    Lösung:
    257 178 76 -39 -6

*Bitte nehmen Sie zur Kenntnis, dass die erste `5` keine Temperatur ist, sondern die Anzahl der nachfolgend zu konvertierenden Werte darstellt!*

