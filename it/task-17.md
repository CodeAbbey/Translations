I checksum sono piccoli valori calcolati da una grande quantità di dati, per verificare se i dati sono coerenti
ovvero se contengono errori.

Ad esempio, se Anna invia un file a Bob, può calcolarne il checksum e comunicarlo a Bob, che
calcolerà il checksum del file ricevuto, e lo confronterà con il valore comunicato da Anna.

_Altro esempio comune - qualsiasi carta di credito che utilizzi ha un checksun nell'ultima cifra del suo numero quindi qualsiasi
dispositivo potrebbe impedirti di inserire un numero errato per errore (puoi approfondire l'argomento nell'esercizio
[Luhn Algorithm](./luhn-algorithm))._

Per programmare diverse altre attività, utilizzaremo un metodo simile per verificare se l'array è corretto o no. Per
evitare problemi con tali attività, ora esercitiamoci con l'algoritmo di calcolo del checksum che verrà utilizzato.

###Enunciato del problema

Vi verrà fornito l'array per il quale calcolare il checksum. Eseguite il calcolo come segue:
per ogni elemento dell'array (partendo dall'inizio) aggiungete questo elemento alla variabile `result` e moltiplicate questa somma
per `113` - questo nuovo valore calcolato con modulo `10000007` dovrebbe diventare il nuovo valore di `result`, e così via.

Leggi l' [articolo sul checksum](../wiki/checksum) per un adescrizione dettagliata di questo algoritmo.
Li puoi trovare anche un'esempio di calcolo.

**Dati Input** indicheranno la lunghezza di un array nella prima riga.  
I valori dell'array seguono nella seconda riga, separati da spazi.  
**Risposta** dovrebbe avere un'singolo valore: il checksum calcolato.

Esempio:

    dati input:
	6
	3 1 4 1 5 9
	
	risposta:
	8921379

_Tutti i valori di input sono compresi tra `0` e `1,000,000,000` - assicurarsi di prestare attenzione ai possibili overflow 

durante i calcoli!_
