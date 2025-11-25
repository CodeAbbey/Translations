_Questo problema è stato gentilmente creato da [**Clive Fraser**](/index/user_profile/csfpython) - many thanks!_

Il robot Alfie lavora in un grande complesso industriale. Il complesso è un quadrato di 5 km di lato. Il compito di Alfie è quello di raccogliere articoli parzialmente o completamente finiti da un punto di raccolta/consegna del complesso e di consegnarli a un altro punto. Il complesso industriale ha diverse corsie che corrono parallele ai lati del quadrato: una da est a ovest e l'altra da nord a sud. Quindi queste corsie si incrociano sempre ad angolo retto. Le corsie corrono sopra l'area di lavoro della fabbrica in modo che Alfie possa muoversi senza interferire con nessuna delle aree di lavoro. I punti di raccolta/consegna sono tutti posizionati all'intersezione dei due insiemi di corsie. Alfie sceglierà sempre la distanza più breve tra due punti, ma è vincolato a seguire le corsie; quindi deve sempre viaggiare parallelamente a uno dei bordi del quadrato. I punti di ritiro/consegna sono distinti dalle loro coordinate (x,y), dove x e y sono rispettivamente le distanze (in metri) a est e a sud di uno degli angoli del quadrato che ha coordinate (0,0). 

Alfie ha la sua stazione di attracco nel punto (0,0). Una volta arrivato alla stazione di attracco, ad Alfie viene inviato un elenco delle consegne da effettuare. Ognuna di queste indica le coordinate del punto di ritiro/consegna in cui deve ritirare un pacco e le coordinate del punto in cui il pacco deve essere consegnato. Per migliorare l'efficienza, ogni consegna viene spedita in una cassa di dimensioni standard. All'interno della cassa possono esserci molti articoli, ma Alfie considera una cassa come un'unica consegna. Se un punto di ritiro/consegna deve inviare più casse alla stessa destinazione, ciascuna di queste deve essere elencata come una consegna separata. Alfie è progettato per poter trasportare due casse (al massimo) contemporaneamente. 

When Alfie gets a list of deliveries he uses a specially designed software package to work out the optimum route for the collection and delivery of all of the crates. The route takes him from his docking station, through all of the collections and deliveries and then back to the docking station. The software ensures that Alfie will never need to be carrying more than 2 crates. The software also ensures that the total distance travelled by Alfie is a minimum.

Quando Alfie riceve un elenco delle consegne, utilizza un software appositamente progettato per calcolare il percorso ottimale per il ritiro e la consegna di tutte le casse. Il percorso lo porta dalla sua stazione di attracco, attraverso tutti i ritiri e le consegne, per poi tornare alla stazione di attracco. Il software garantisce che Alfie non debba mai trasportare più di 2 casse. Il software garantisce inoltre che la distanza totale percorsa da Alfie sia minima. 

In questo problema ti verrà fornito un elenco delle consegne per Alfie e ti verrà chiesto di calcolare la distanza percorsa da Alfie per effettuare tutte le consegne, partendo dalla stazione di attracco e tornandovi.

La prima riga del problema sarà un singolo intero N che indica il numero di ritiri e consegne da effettuare. Ciascuna delle successive N righe sarà composta da quattro interi X1, Y1, X2 e Y2, separati da spazi. (X1,Y1) indica la posizione del punto da cui deve essere ritirata una cassa. (X2,Y2) indica la posizione del punto in cui la stessa cassa deve essere consegnata. Il risultato è la lunghezza (in metri) del percorso ottimale seguito da Alfie per completare l'elenco delle consegne e tornare alla stazione di attracco. 

Nell'esempio seguente, N = 3, quindi ci sono 3 casse da ritirare e consegnare. Il percorso ottimale ha una lunghezza di 18206 metri e viene eseguito come descritto nella tabella seguente. (Nota che le casse trasportate si riferiscono al numero di casse trasportate da Alfie, dopo aver raggiunto la posizione indicata) 

	  Posizione	Distanza Totale	Colli trasportati
	
	      (0,0) 		    0 	       0	Inizia alla stazione di attracco
	  (737,482) 	     1219 	       1	Raccogli la cassa numero 2
	(3855,4069) 	     7924 	       2	Raccogli la cassa numero 1 
	(4230,4175)	         8405 	       1	Consegna la cassa numero 2 
	(4837,3926) 	     9261 	       2	Raccogli la cassa numero 3 
	(2127,1979) 	    13918 	       1	Consegna la cassa numero 3 
	(1542,2070) 	    14594 	       0	Consegna la cassa numero 1 
	      (0,0) 	    18206 	       0	Ritorna alla stazione di attracco 

Esempio:

	input:
	3
	3855 4069 1542 2070
	737 482 4230 4175
	4837 3926 2127 1979
	
	risposta:
	18206
