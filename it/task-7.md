<!-- #Da Fahrenheit a Celsius -->
Questo esercizio di programmazione è all'incirca lo stesso delle somme in cicli, ma richiede un po' più di calcoli.

<div class="text-center">
	<img alt="fahrenheit e celsius" src="https://codeabbey.github.io/data/fahrenheit_celsius.png"/>
</div>

*Nota: il problema di [Arrotondamento](./rounding--it) spiega l'algoritmo di arrotondamento utilizzato anche 
in questo esercizio.*

Ci sono due sistemi diffusi per misurare la temperatura: Celsius e Fahrenheit. Il primo è molto popolare in Europa
e il secondo è utilizzato prevalentemente negli Stati Uniti.

Per la scala Celsius l'acqua ghiaccia a 0 gradi e bolle a 100 gradi. Per Fahrenheit l'acqua ghiaccia a 32 gradi e 
bolle a 212 gradi. Puoi imparare di più dalla pagina [wikipedia su Fahrenheit][wiki]. Usa questi due punti per
convertire altre temperature.

[wiki]: https://it.wikipedia.org/wiki/Grado_Fahrenheit

Lo scopo è scriver eun programma che converta i gradi da Fahrenheit a Celsius

I **dati di input** contengono `N+1` valori, il primo è il numero `N` casi d calcolare (**Nota** che non dovresti convertirlo).
La **risposta** dovrà contenere esattamente `N` risultati, arrotondati all'intero più vicino e separati da spazi.

Esempio:

    dati:
    5 495 353 168 -39 22
    risposta:
    257 178 76 -39 -6

*Nota bene che il primo `5` non è una temperatura, ma il numero di calori da convertire!*
