<!-- # Triple Pitagoriche -->
*Questo compito è ispirato alla discussione nel [Blog sugli algoritmi di Faisal Rahman](http://algoexplode.wordpress.com/) su un compito simile da
[ProjectEuler](http://projecteuler.net/problem=9)*

Come sappiamo, il [Teorema di Pitagora](./pythagorean-theorem) ci parla della semplice equazione:

    a^2 + b^2 = c^2

Esistono realmente terne `a, b, c` di numeri **interi** che soddisfano questa equazione. Questo non è un fatto ovvio,
inoltre non esistono terne di questo tipo per altre potenze eccetto `2` - questo è il famoso
[Teorema di Fermat](http://en.wikipedia.org/wiki/Fermat's_Last_Theorem) che non poté essere risolto per più di `350`
anni.

Tuttavia, per la potenza di `2` esistono innumerevoli terne di questo tipo. Una di queste, per esempio, `3, 4, 5`.

Tuttavia, non è sempre facile trovare una terna che soddisfi alcune condizioni specifiche:

**In questo problema devi scrivere un programma che, dato il valore di `s = a + b + c`
trovi l'unica terna che soddisfa l'equazione.**

Ad esempio, data la somma di `12`, si adattano solo `3, 4, 5`, per la somma di `30` si adattano solo `5, 12, 13` ecc.

**I dati di input** conterranno il numero di casi di test nella prima riga.
Le altre righe conterranno un singolo valore ciascuna, la somma per la quale si desidera trovare la tripla.
**La risposta** dovrebbe contenere i valori di `c^2` per ogni tripla trovata (ovviamente è uguale a `a^2 + b^2`),
separati da spazi.

**Nota:** i valori reali di `s` sarebbero sufficientemente grandi, circa `10e+7`, quindi le soluzioni più semplici potrebbero essere inefficienti.

Esempio:

    dati input:
	2
	12
	30
	
	risposta:
	25 169

