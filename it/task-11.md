<!-- #Somma delle cifre -->
Questo esercizio di programmazione ha lo scopo di introdurre le basi del sistema numerico. Inizieremo ad apprendere
questo concetto giocando con il sistema decimale che usiamo quotidianamente (anche se è importante tenere presente che il computer
non lo utilizza internamente, ma converte i numeri in esso solo quando devono essere mostrati all'utente).

Poiché qualsiasi numero maggiore di 9 è rappresentato da più cifre, possiamo calcolare la somma di queste cifre. Ad esempio,
per i numeri `1492` e `1776` otteniamo:

    1 + 4 + 9 + 2 = 16
	1 + 7 + 7 + 6 = 21

In questo compito ti verranno forniti diversi numeri e ti verrà chiesto di calcolare la somma delle loro cifre.

**Importante:** sebbene molti linguaggi di programmazione abbiano funzioni integrate per convertire i numeri in stringhe
(da cui è possibile estrarre cifre), non dovresti usarle (dato che il tuo obiettivo è imparare alcuni trucchi di programmazione).

**Invece** è necessario implementare un algoritmo con divisione ripetitiva per 10 (base del sistema numerico) e somma dei
resti. Leggi l'articolo [Numero in cifre][numtodig] per i dettagli sull'algoritmo.

[numtodig]: ../wiki/number-to-digits

###Enunciato del problema

**Datidi input** saranno nel seguente formato:

- la prima riga contiene `N`, il numero di valori da elaborare;
- seguiranno le righe `N` che descrivono i valori per i quali la somma delle cifre deve essere calcolata con `3` numeri interi `A B C`;
- per ogni caso è necessario moltiplicare `A` per `B` e aggiungere `C` (ovvero `A * B + C`), quindi calcolare la somma delle cifre del risultato.
  
**Risposta** dovrebbe avere `N` risultati, separati da spazi. Ad esempio:

    dati di input:
	3
	11 9 1
	14 90 232
	111 15 111
	
	risposta:
	1 16 21


Qui il primo caso richiede di calcolare `11*9+1 = 100` e la sua somma di cifre è `1+0+0 = 1`.
