<div class="centered">
<iframe width="420" height="315" src="//www.youtube.com/embed/G4w8MZ9TIaI" frameborder="0" allowfullscreen></iframe><div class="hint">Pentru mai multe explicații, urmărește acest video</div>
</div>

In această problemă vei face cunoștință cu un algoritm foarte popular numit "căutare liniară" sau "linear search". Acest algoritm este foarte des folosit în cadrul unor sarcini mai complexe (sortarea datelor etc)

Foarte des avem nevoie să cunoaștem valoarea maximă sau minimă dint-un ansamblu de numere sau dintr-un tablou. Pentru a rezolva această problemă, trebuie să salvăm **valoarea maximă curentă** (sau valoare minimă) intr-o variabilă, iar apoi să parcurgem tabloul și să o comparăm cu fiecare număr din acest tablou. Atunci când un număr este mai mare decăt **valoarea maximă curentă**, acest numar devine noua valoare maximă.

O dată ce toate valorile au fost epuizate, această variabilă temporară va conține numarărul maxim din tablou.

**Datele de intrare** conțin pe o singură linie, exact `300` de numere.  
**Răspunsul** ar trebui să conțină numărul maxim si numărul minim din acest tablou, separate print spațiu.

Exemplu:

	Date de intrare:
	1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2
	
	Răspuns:
	300 1
