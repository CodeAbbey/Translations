<!-- #Fahrenheit to Celsius -->
Questo esercizio di programmazione è più o meno lo stesso del conteggio delle somme in un ciclo, ma richiede qualche calcolo in più.

<div class="text-center">
	<img alt="fahrenheit and celsius" src="https://codeabbey.github.io/data/fahrenheit_celsius.png"/>
</div>

*Nota: il problema [Rounding](./rounding) spiega l'algoritmo di arrotondamento utilizzato in questa attività.*

Esistono due sistemi di misurazione della temperatura molto diffusi: Celsius e Fahrenheit. Il primo è molto diffuso in Europa,
mentre il secondo è molto utilizzato, ad esempio, negli Stati Uniti.

Secondo la scala Celsius, l'acqua congela a 0 gradi e bolle a 100 gradi. Secondo la scala Fahrenheit, l'acqua congela
a 32 gradi e bolle a 212 gradi. Puoi trovare maggiori informazioni su [wikipedia on Fahrenheit][wiki]. Usa questi due punti
per la conversione di altre temperature.

[wiki]: http://en.wikipedia.org/wiki/Fahrenheit

Devi scrivere un programma per convertire i gradi Fahrenheit in Celsius.

I **dati di input** contengono `N+1` valori, il primo dei quali è `N` stesso (**Nota**: non dovresti provare a convertirlo).
La ​​**risposta** dovrebbe contenere esattamente `N` risultati, arrotondati all'intero più vicino e separati da spazi.

Esempio:

    dati input:
    5 495 353 168 -39 22
    risposta:
    257 178 76 -39 -6


*Si prega di notare che il primo `5` non è una temperatura, ma la quantità di valori da convertire!*
