<!-- #Code Guesser -->
Se conoscete il vecchio gioco [Bulls and Cows](./bulls-and-cows), questo problema di programmazione vi sembrerà familiare.

Andrew e Peter giocano a indovinare il codice. Andrew sceglie un `numero segreto` composto da `3` cifre. Peter cerca di
indovinarlo, proponendo diversi valori, uno alla volta.

Per ogni `ipotesi` Andrew deve dire quante cifre sono corrette, ovvero **sono le stesse** nel valore proposto e nel suo
numero segreto, e sono posizionate nella **stessa posizione**. Ad esempio, se il numero segreto è `125` e Peter dice `523`, allora
Andrew risponde con `1`. Ecco un esempio del gioco:

    Andrea sceglie un numero segreto: 846
	
	Ipotesi diPeter             Risposta diAndrew
	      402                        0
		  390                        0
		  816                        2
		  848                        2
		  777                        0
		  815                        1
    	  846                        3

Quindi Peter ha indovinato il numero corretto dopo `6` tentativi.

Devi scrivere un programma che legga le ipotesi fornite da Peter (tranne l'ultima) e stampi il numero segreto
scelto da Andrew. È garantito che esista esattamente una soluzione.

I **dati di input** conterranno il numero di ipotesi nella prima riga.
Seguiranno poi le risposte con i relativi tentativi, ciascuna contenente il numero fornito da Peter e la risposta data da Andrew.
A differenza degli esempi, i numeri saranno composti da `4` cifre.
La **risposta** dovrebbe contenere il numero segreto (anch'esso di `4` cifre). Vedi esempio:

    dat input:
	6
	402 0
	390 0
	816 2
	848 2
	777 0
	815 1
	
	risposta:
	846


*Qui utilizziamo valori a 3 cifre per brevità, ma l'algoritmo è lo stesso.*

