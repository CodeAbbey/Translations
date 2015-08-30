<!-- #Fahrenheit zu Celsius -->
Diese Programmierübung ist ähnlich zur Aufgabe "Summieren in Schleife" ("counting sums in loop"), 
bedarf aber ein wenig mehr Berechnungen


<div class="text-center">
	<img alt="fahrenheit und celsius" src="http://s5.postimg.org/3tpo5bg6v/fahrenheit.png"/>
	<div class="hint">Anmerkung: Die Übung <a href="./rounding--de">Rundung</a> erklärt den Rundungs-Algorythmus
	den wir in dieser Aufgabe nun wieder benutzen werden.</div>
</div>

Zur Messung von Temperaturen gibt es zwei weitverbreitete Systeme - Celsius and Fahrenheit.
Das erste ist weit verbreitet in Europa und weltweit, während das zweite vor allem in den Britisch geprägten
Gebieten wie USA zu finden ist. 

Auf der Celsius Skala friert Wasser bei genau 0 Grad C und kocht bei 100 Grad C. Auf der Fahrenheit Skala
friert Wasser bei 32 Grad F und kocht bei 212 Grad F. Mehr darüber können Sie im Wikipedia Beitrag 
[Grad Fahrenheit](https://de.wikipedia.org/wiki/Grad_Fahrenheit) nachlesen. 

Verwenden Sie diese Punkte für ihre Umrechnung von Temperaturen. 


Die Aufgabe besteht nun darin, ein Programm zu schreiben welches Fahrenheit in Celsius umrechnen kann. 

**Eingabe Daten** enthalten `N+1` Werte, der erste davon ist `N` selbst. (**Beachten Sie** das Sie diesen nicht convertieren).  
**Lösung** enthält genau `N` Resultate, gerundet auf die nächst nähere Ganzzahl und durch Leerzeichen getrennt. 

Beispiel:

    Eingabe Daten:
    5 495 353 168 -39 22

    Lösung:
    257 178 76 -39 -6

*Bitte nehmen Sie zur Kenntnis, dass die erste `5` keine Temperatur ist, sondern die Anzahl der nachfolgend zu konvertierenden Werte darstellt!*

