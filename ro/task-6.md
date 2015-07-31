Atunci când un program conține numere care au o parte fracționară, preferăm uneori să **rotunjim** asemenea valori la cel mai apropiat număr întreg, deoarece nu ne înteresează zecimalele. Vom folosi acest procedeu ulterior, în cadrul altor probleme (pentru a simplifica răspunsurile).

Datele de intrare consistă din câteva perechi de numere. Pentru fiecare pereche, sarcina ta este să împarți primul număr la al doilea și să rontunjești câtul **la cel mai apropiat** număr întreg.

În cazul in care partea fracționară este exact `0.5`, numărul ar trebui rotunjit prin adaos (poți aduna `0.5` la numărul inițial). Pentru numerele negative "mai mare" înseamna "mai aproape de zero". Poți consulta acest articol pe Wikipedia despre [Rounding](http://en.wikipedia.org/wiki/Rounding#Round_half_up) pentru mai multe explicații.

Dacă in problemele viitoare va fi necesară rotunjirea rezultatului, poți folosi acest procedeu (excepție fiind cazul în care un alt procedeu este specificat)

**Datele de intrare** conțin pe o singură linie numărul de perechi.  
Următoarele linii conțin perechile de numere propriu-zise.  
**Răspunsul** ar trebui să conțină câtul fiecarei perechi, rotunjit prin procedeul descris mai sus si separat prin spațiu.

Exemplu:

	Date de intrare:
	3
	12 8
	11 -3
	400 5
	
	Răspuns:
	2 -4 80
