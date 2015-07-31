<!-- #Fahrenheit to Celsius -->
Acest exercițiu este similar exercițiului **sums in loop**, dar necesită mai multe calcule.

<div class="text-center">
	<img alt="fahrenheit and celsius" src="http://s5.postimg.org/3tpo5bg6v/fahrenheit.png"/>
</div>

*Notă: Problema [Rounding](./rounding) explică algoritmul folosit pentru rotunjirea rezultatelor.*

Există doua sisteme răspandite pentru a măsura temperatura, Celsius și Fahrenheit. Primul este folosit cu preponderență în Europa, al doilea fiind folosit in Statele Unite ale Americii și în alte câteva țări.

Conform sistemului Celsius, punctul de înghețare al apei este la 0 grade și punctul ei de fierbere la 100 de grade. Conform sistemului Fahrenheit punctul de înghețare al apei este la 32 de grade și punctul ei de fierbere la 212 grade. Poți afla mai multe detalii despre [sistemul Fahrenheit][wiki] pe wikipedia. Folosește aceste detalii pentru a converti temperatura dintr-un sistem în altul.

[wiki]: http://en.wikipedia.org/wiki/Fahrenheit

Sarcina ta este să scrii un program care va realiza în mod automat aceasta conversie din Fahrenheit în Celsius.

**Datele de intrare** conțin `N+1` valori, prima valoare fiind însuși `N` adica numărul total de valori (**Notă** această valoare nu ar trebui sa fie tratată).  
**Răspunsul** ar trebui să conțină exact `N` rezultate, fiecare dintre ele rotunjit la cel mai apropiat număr întreg si separate prin spațiu.

Exemplu:

    Date de intrare:
    5 495 353 168 -39 22
    
    Răspuns:
    257 178 76 -39 -6

*Remarcă: primul `5` nu este o temperatură ci numărul total de valori care urmează a fi convertite!*