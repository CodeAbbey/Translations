Quando parliamo di **progressione aritmetica** (o sequenza aritmetica) intendiamo una serie
di numeri con una proprietà speciale: ogni valore è seguito dall'altro, maggiore di un valore predefinito
(passo).

Cioè la differenza tra il valore `(K+1)`-esimo e il valore `K`-esimo è una costante. Ecco alcuni esempi di sequenze

	1 2 3 4 5 6 7 ...
	4 6 8 10 12 14 16...
	10 13 16 19 22 25 28...

Pertanto, la sequenza aritmetica è completamente definita dal primo elemento (`A`) e dal valore di incremento
- passo - (`B`). I primi elementi potrebbero essere espressi come

    A + (A + B) + (A + 2B) + (A + 3B) + ...

Devi calcolare la somma dei primi elementi di una sequenza aritmetica.
[Pagina di Wikipedia][wiki] sulla progressione aritmetica potrebbe essere di grande aiuto per chi
la incontra per la prima volta.

[wiki]: http://en.wikipedia.org/wiki/Arithmetic_progression

**Dati di input:** la prima riga contiene il numero di casi di test.
Le altre righe contengono casi di test sotto forma di triplette di valori `A B N` dove `A` è il primo valore della sequenza,
`B` è la dimensione del passo e `N` è il numero di primi valori da considerare.
**Risposta:** si devono ottenere i risultati (somme dei primi `N` elementi) per ogni sequenza, separati da spazi.


Esempio:

    dati:
    2
    5 2 3
    3 0 10
    
    risposta:
    21 30

_Spiegazione dell'esempio. Nel primo caso abbiamo una sequenza che inizia con `5` e aumenta di `2` ogni volta.
Vogliamo sommare `3` elementi da essa `5 + 7 + 9 = 21`. Il secondo è più semplice. Inizia con `3` ma l'incremento è `0`,
quindi è `3 + 3 + ... + 3 = 30` (totale di `10` elementi)._

