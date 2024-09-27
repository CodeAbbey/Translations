<!-- #Progressione aritmetica -->
Quando parliamo di **progressione aritmetica** (o sequenza aritmentica) intendiamo una serie
di numeri con una proprietà speciale -  ogni valore è seguito da un altro, incrementato da una 
quantità prestabilita (valore incrementale).

Cioè quando la differenza tra gli `(K+1)`-esimi e `K` -esimi valori è costante. Di seguito alcuni 
esempi di sequenze

	1 2 3 4 5 6 7 ...
	4 6 8 10 12 14 16...
	10 13 16 19 22 25 28...

 una progressione aritmetica è completamente definita dal primo membro (`A`) e dal valore
 incrementale - quantità dell'incremento - (`B`). La sequenza può quindi essere espressa come

    A + (A + B) + (A + 2B) + (A + 3B) + ...

Dovrai quindi calcolare la somma fino ad un certo termine della prograssione aritmetica.
La [pagina Wikipedia][wiki] sulle progressioni aritmetiche può essere di aiuto per chi le incontra
per la prima volta.

[wiki]: https://it.wikipedia.org/wiki/Progressione_aritmetica

**Dati di input:** la prima riga contiene il numero di casi da testare.
Le rimanenti righe contengono i casi da testare in forma di triplette `A B N` dove `A` è il primo valore della
sequenza, `B` è il valore incrementale e `N` è il numero di termini della serie da calcolare.
**Risposta:** dovrai inserire i risultati (la somma dei primi `N` termini) di ciascuna sequenza, separati da spazi.

Esempio:

    dati:
    2
    5 2 3
    3 0 10
    
    risposta:
    21 30

_Spiegazione dell'Esempio. Nel primo caso abbiamo una sequenza che inizia con `5` e incrementa di `2` ogni volta.
Vogliamo la somma dei primi `3` elementi `5 + 7 + 9 = 21`. Nel secondo caso è più semplice. Parte da `3` ma
l'incremento è `0`, quindi sarà `3 + 3 + ... + 3 = 30` (il totale dei primi `10` elementi)._
