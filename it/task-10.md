<!-- #Funzione lineare -->
Un problema molto comune nella programmazione computazionale è determinare la legge di base a cui obbedisce un fenomeno.
A scopo didattico, esercitiamoci con una semplice variante: scoprire la dipendenza lineare tramite due osservazioni date (ad esempio, come il
prezzo di un prodotto dipende dalle sue dimensioni, dal suo peso, ecc.)

La funzione lineare è definita dall' equazione:

    y(x) = ax + b

Dove `a` e `b` sono delle costanti.
Ad esempio, con `a=3, b=2` la funzione produrrà i valori `y = 2, 5, 8, 11...`
per `x = 0, 1, 2, 3...`

Il tuo compito è determinare `a` e `b` tramite due punti appartenenti alla funzione.
Ovvero, ti vengono fornite due coppie di valori `(x1, y1), (x2, y2)` che soddisfano l'equazione della funzione
- e dovresti ripristinare l'equazione stessa.

**I dati di input** contengono il numero di casi di test nella prima riga
e poi i casi di test stessi in righe separate.
Ogni caso contiene `4` numeri interi (`x1 y1 x2 y2`).
**Anche le risposte** devono essere numeri interi e vanno scritte in riga, separate da spazi e racchiudendo ogni coppia tra parentesi, ad esempio:
    dati input:
    2
    0 0 1 1
    1 0 0 1
    
    risposte:
    (1 0) (-1 1)

