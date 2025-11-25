Questo problema introduce il popolare algoritmo della "ricerca lineare" che dovrebbe essere appreso a fondo e come spesso accade
utilizzato nella programmazione di compiti più complessi (ordinamento ecc.).

Operazione molto comune su sequenza di valori, o array è quello di trovare il valore minimo o massimo. Per farlo ho bisogno di 
memorizzare **massimo corrente** (o minimo) in una variable, e quindi scorrere attraverso l'array, confrontando ciascun valore
con questa variabile. Ogni volta che il valore successivo è superiore a quello della variabile temporanea questo valore 
dovrebbe essere copiato in essa (come nuovo massimo).

Alla fine del passaggio questa variabile temporanea manterrà il valore estremo (min o max.

**Dati Input** ti daranno esattamente `300` numeri in una singola riga.  
**Risposta** dovrebbe contenere il massimo e il minimo di questi valori, separati da spazio.

<span class="red">Importante:</span> a questo problema alcuni chiedono **"Come devo copiare tanti numeri nel mio codice, come creo
un array / elenco dei numeri..."**  
Ti prego, non fare così! Invece [**Guarda il mio video demo**](https://www.youtube.com/watch?v=c6WWZe12ves)
(dal minuto 4:00) puoi vedere come usiamo lo
standard input per leggere i numeri quando si esegue on-site!

**Esempio:**

	dati di input:
	1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2
	
	risposta:
	300 1
