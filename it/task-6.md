Quando un programma gestisce numeri che hanno una parte frazionaria, a volte vogliamo **arrotondare** a numeri 
interi. Questo ci servirà per programmare alcuni problemi successivi (ad esempio per semplificare delle risposte), quindi
svolgiamo il seguente esercizio dedicato per imparare questo trucco.

Ci sono diverse coppie di numeri. Per ogni coppia devi dividere il primo per il secondo e restituire
il risultato arrotondato all'intero **più vicino**.

Nel caso in cui il risultato contenga esattamente `0.5`, il valore deve essere arrotondato "per eccesso"
(ad esempio aggiungendo `0.5` se positivo o sottraendolo se negativo).
Per spiegazioni approfondite, consultare l'articolo di Wikipedia [Arrotondamento - per eccesso](https://en.wikipedia.org/wiki/Rounding#Rounding_half_away_from_zero).
In qualsiasi altro problema, quando si parla di arrotondamento, si suppone che venga utilizzato lo stesso algoritmo
di arrotondamento (a meno che non venga specificato esplicitamente altro).

**Dati Input** forniranno il numero di casi di test nella prima riga.  
Le righe successive conterranno un caso di test (ovvero la coppia di numeri) ciascuna.  
**Risposta** dovrebbe contenere i risultati della divisione e dell'arrotondamento per ciascuna coppia separati da spazi.

Esempio:

	dati input:
	3
	12 8
	11 -3
	400 5
	
	risposta:
	2 -4 80
