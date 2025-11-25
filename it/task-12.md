Gestire i resti può causare grossi grattacapi ai programmatori alle prime armi. Scriviamo un semplice programma che
ha questa operazione al suo centro per studiare meglio la divisione intera. Allo stesso tempo, faremo un po' di pratica nella
gestione delle date, che a volte crea grattacapi anche ai programmatori più esperti.


In aritmetica, il resto (o modulo) è la quantità "rimasta" dopo aver eseguito la divisione di due numeri interi
che non sono divisibili in parti uguali (da [Wiki][wiki]). Questo esercizio fornirà ulteriore pratica con l'operazione modulo.

[wiki]: http://en.wikipedia.org/wiki/Remainder

Supponiamo di ricevere due timestamp, ad esempio quando il treno o il traghetto inizia il suo viaggio e quando lo termina.
Potrebbe apparire così:

    start: May 3, 17:08:30
	end  : May 8, 12:54:15

E siamo curiosi di sapere quanto tempo (in giorni, ore, minuti e secondi) viene impiegato per viaggiare (forse, per
scegliere una variante più veloce). Come si potrebbe ottenere questo risultato?

Uno dei modi più semplici è:

- convertire entrambi i timestamp in numeri grandi, che rappresentano i secondi dall'inizio del mese (o dell'anno o del secolo);
- calcolare la loro differenza, ovvero il tempo di percorrenza in secondi;
- riconvertire questa differenza in giorni, ore, minuti e secondi.

La prima operazione potrebbe essere eseguita moltiplicando i minuti per `60` e le ore per `60*60` ecc. e sommando tutti i valori.
La terza operazione dovrebbe essere eseguita al contrario, eseguendo diverse divisioni mantenendo i resti.

In questo compito ci vengono fornite diverse coppie di timestamp. Supponiamo che entrambe le date della coppia siano sempre nello
stesso mese, quindi verrà fornito solo il numero del giorno. Vogliamo calcolare la differenza tra i timestamp in ciascuna coppia.

**Dati di input:** la prima riga contiene il numero di casi di test, le altre righe contengono i casi di test stessi.
Ogni caso di test contiene `8` numeri, `4` per ogni timestamp: `giorno1 ora1 min1 sec1 giorno2 ora2 min2 sec2` (il secondo
timestamp sarà sempre successivo al primo).
**Risposta:** per ogni caso di test, la differenza deve essere visualizzata come segue `(giorni ore minuti secondi)` - si prega di
notare le parentesi quadre - separate da spazi.

Esempio:

    dati input:
    3
	1 0 0 0 2 3 4 5
    5 3 23 22 24 4 20 45
    8 4 6 47 9 11 51 13
    
	risposte:
    (1 3 4 5) (19 0 57 23) (1 7 44 26)

