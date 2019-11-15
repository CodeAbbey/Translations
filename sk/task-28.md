Poďme použiť naše programátorské skúsenosti na nejaký kvázi-vedecký problém - pretože čisto abstraktné
veci sú trošku nudné.

Jednoduché meranie indexu telesnej hmotnosti bolo navrhnuté v strede XIX storočia. Záleží iba na výške a
hmotnosti dotyčnej osoby - v angličtine nazývané **Body Mass Index** alebo **BMI**. Je definované ako:

    BMI = váha / výška^2

Pričom váha je v `kilogramoch` a výška v `metroch`.

Medzi telesné stupne patria:

	Podvýživa       -           BMI < 18.5
	Normálna váha   -   18.5 <= BMI < 25.0
	Nadváha         -   25.0 <= BMI < 30.0
	Obezita         -   30.0 <= BMI

Napríklad, ak vážim  `80 kg` a mám výšku `1.73 m` môžem vypočítať:

    BMI = 80 / (1.73)^2 = 26.7

t.j. mierna nadváha.

O správnosti alebo nesprávnosti tohoto merania nebudeme diskutovať. Namiesto toho vypočítajte miery pre 
niekoľko ľudí.

**Vstupné dáta** obsahuje počet ľudí na prvom riadku.  
V každom ďaľšom riadku budú dve hodnoty - váha v kilogramoch a výška v metroch.  
**Odpoveď** by mala obsahovať text `under` pre podvýživu, `normal` pre normálnu váhu,
`over` pre nadváhu a `obese` pre obezitu pre každý korešpondujúci príklad, oddelený medzerami.
Napríklad:

    vstupné dáta:
	3
	80 1.73
	55 1.58
	49 1.91
	
	odpoveď:
	over normal under
