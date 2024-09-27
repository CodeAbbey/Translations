<!-- #Arrotondamento -->

Quando programmando abbiamo a che fare con numeri con una parte decimale in alcuni casi è utile **arrotondare** questi 
numeri all'intero più vicino. Questo ci servirà per altri programmi in futuro (per rendere le risposte più semplici, 
per esempio), quindi usiamo questo esercizio per fare esperienza con questoo trucchetto.

Ci sono diverse coppie di numeri. Per ciascuna coppia devi dividere il primo per il secondo e restituire 
il risultato, arrotondato **al più vicino** intero.

Quando il risultato della divisione restituisce esattamente `0.5` come parte frazionaria, devi arrotondare 
al'intero superiore (per esempio sommandogli `0.5`). Da notare che per valori negativi "arrotondare 
all'intero superiore" si intende "più vicino allo zero". Fai riferimento alla pagina Wikipedia [Arrotondamento](https://it.wikipedia.org/wiki/Arrotondamento)
per avere una spiegazione più dettagliata.

Quando l'arrotondamento sarà menzionato nei problemi successivi, si intenderà lo stesso algoritmo qua 
descritto (a meno che non sia esplicitamente specificato diversamente).

I **dati di input** conterranno nella prima riga il numero totale di coppie da processare.
Le righe seguenti conterranno le coppie di valori da testare.
La **risposta** dovrà contenere i risultati delle divisioni arrotondati per ciascuna coppia,
separati da spazi.

Esempio:

	dati di input:
	3
	12 8
	11 -3
	400 5
	
	risposta:
	2 -4 80
