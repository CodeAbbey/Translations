<div class="centered">
<img alt="dimostraione della somma di un vettore" src="https://codeabbey.github.io/data/sum_in_loop.gif"/>
</div>

Adesso il nostro obbiettico è di imparare i **cicli** - cioè le azioni ripetute.
Scopriamo come sommare diversi numeri (più di due). Per farlo sarà utile utilizzare un ciclo.
Come mostrato in alto nella figura - puoi creare una variabile `Sum` e sommargli ciascun valore della lista.
Il [ciclo "for"](http://it.wikipedia.org/wiki/Ciclo_for) può adattarsi bene allo scopo siccome conosciamo 
in anticipo il numero dei numeri da sommare. 

Se hai problemi puoi provare prima [Sums In Loop](./sums-in-loop) - potresti trovarlo più semplice.

I **dati di input** hanno il seguente formato:

- la prima riga contiene `N` - numero totale dei valori da sommare;
- la seconda linea contiene gli `N` valori.

La **risposta** deve contenere un singolo valore - La somma degli `N` valori.

Esempio:

	dati di input:
	8
	10 20 30 40 5 6 7 8
	
	risposta:
	126
  
**Nota** siccome ci sono diverse dozzine di numeri, non dovresti copiarli manualmente nel tuo programma.
Dovresti invece farli leggere al tuo programma usando un campo di input (dove potrai incollarli 
direttamente tutti in una volta). Nota che se fai girare il tuo codice sul nostro server, i dati saranno 
automaticamente incollati come input standard per semplicità.
