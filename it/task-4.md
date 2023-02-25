<!-- #Minimo di Due -->
<div class="text-center">
	<img src="https://codeabbey.github.io/data/min_of_two.gif" alt="Animazione sulla scelta del minimon"/>
</div>

La maggior parte dei programmi dovrebbe essere in grado di compiere più azioni e prendere più decisioni. 
Ora andremo a fare pratica con la programmazione condizionale.
Questa logica normalmente è realizzata da un'istruzione `SE ... OPPURE` che potrebbe apparire così:

    SE qualche_condizione ALLORA
	    fai_qualcosa
	OPPURE
	    fai_qualcos_altro
	FINE_SE

A seconda del lingaggio di programmazione che hai scelto la sintassi potrebbe essere differente e la parte `oppure`
è quasi sempre opzionale.
Puoi leggere di più sull'argomento nell'articolo wikipedia [Selezione][cond].

[cond]: https://it.wikipedia.org/wiki/Selezione_(informatica)

Dei due numeri, per favore, seleziona quello con il valore minimo. Ecco diverse coppie di numeri per un test approfondito.

I **dati di input** conterranno nella prima riga il numero totale di coppie da processare.
Le righe seguenti conterranno le coppie di valori da confrontare.
Per la **risposta** si dovrà inserire il valore dei minimi valutati separati da spazi, per esempio:

    dati:
	3
    5 3
    2 8
    100 15
    
    risposta:
    3 2 15
