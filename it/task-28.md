Applicheremo le nostre competenze di programmazione a qualche problema quasi scientifico, - dato che è
un po'noioso imparare solo cose astratte.

La semplice misura della costituzione corporea fu proposta a metà del XIX secolo. Dipende solo dall'altezza e
dal peso di una persona - ed è chiamata **Indice di massa corporea** o **BMI**. E' definito come:

    BMI = peso / altezza^2

Dove il peso è espresso in `kilogrammi` e l'altezza in `metri`.

Sono proposti quattro gradi generali:

	Sottopeso  (under)    -           BMI < 18.5
	Normale    (normal)   -   18.5 <= BMI < 25.0
	Sovrappeso (over)     -   25.0 <= BMI < 30.0
	Obesità    (obese)    -   30.0 <= BMI

Ad esempio, se ho un peso di `80 kg` e un'altezza di `1.73 m` Posso calcolare:

    BMI = 80 / (1.73)^2 = 26.7

ovvero leggermente sovrappeso.

Non discuteremo se questa gradazione sia appropriata o meno. Dovresti semplicemente calcolare i voti per diverse
persone.

**Dati Input** contengono il numero delle persone nella prima linea.  
Le altre righe conterranno due valori ciascuna - peso in kilogrammi e altezza in metri.  
**Risposta** dovrebbe contenere le parole `under`, `normal`, `over`, `obese` per ogni caso di test corrispondente,
separate da spazi. Per esempio:

    dati input:
	3
	80 1.73
	55 1.58
	49 1.91
	
	risposta:
	over normal under

