<div class="centered">
<img alt="demo of summing an array" src="https://codeabbey.github.io/data/sum_in_loop.gif"/>
</div>

Ora il nostro obiettivo è imparare i **loop** - ovvero le azioni ripetute.
Cerchiamo di calcolare la somma di più numeri (più di due). Sarà utile farlo in un loop.
Come mostrato nell'immagine sopra,puoi creare la  variable `sum` e aggiungerci tutti i valori dell'elenco.
Forse il ["for" loop](http://en.wikipedia.org/wiki/For_loop) andrà bene, dato che il numero di valori è noto a priori.

In caso di problemi, prova prima [Sums In Loop](./sums-in-loop)- probabilmente è più semplice.

**I dati di input** hanno il seguente formato:

- la prima linea contiene `N` - quantità di valori da sommare;
- la seconda linea contiene `N` valori veri e propri.

**La risposta** dovrebbe contenere un singolo valore: la somma di `N` valori.

Esempio:

	input data:
	8
	10 20 30 40 5 6 7 8
	
	risposta:
	126

**Nota** poichè sono presenti diverse decine di numeri, non dovresti copiarli manualmente nel tuo programma.
Fai invece in modo che il tuo programma li legga dallo standard input(dove puoi copiarli tutti insieme). Tieni presente che
se esegui il codice sul nostro server, i dati vengono automaticamente copiati sullo standard input per comodità.
