Questo programma assomiglia ad algoritmi più complessi per il calcolo del CRC e di altri checksums nonchè a funzioni hash su
stringhe di caratteri. Inoltre fornisce un ulteriore esercizio sulla suddivisione dei valori in cifre decimali. Potresti
provare [Somma delle Cifre](./sum-of-digits) prima di questo.

Calcoliamo la somma delle cifre, come in precedenza, moltiplicando ogni cifra per la sua posizione (contando da sinistra a destra
partendo da  1). Ad esempio, dato il valore `1776` calcoliamo la somma **ponderata** delle cifre (chiamiamola  "wsd") come segue:

	wsd(1776) = 1 * 1 + 7 * 2 + 7 * 3 + 6 * 4 = 60

**Dati di Input** fornirà il numero di test nella prima riga.  
I valori veri si trovano nella seconda riga. Per ciascuno di questi valori si deve calcolare la somma ponderata delle cifre.  
**Risposta:** come di consueto, Inserire i risultati su una riga, separandoli con spazi.

Example:

    dati input:
	3
	9 15 1776
	
	risposta:
	9 11 60

