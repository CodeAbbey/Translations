Táto úloha poskytuje cvičenie pre základnú vlastnosť zvyšku, ktorá sa používa v aritmetike - pozostávajúca zo
zvyšku sčítania a násobenia. Táto dôležitá vlastnosť je často používaná pre kontrolu výsledkov z výpočtov,
v kompetetívnom programovaní, vo výpočte kontrolných súčtov a najmä v šifrovaní. 
Viac (po anglicky) ohľadne modulárnej aritmetiky [v tomto odkaze][modar].

[modar]: ../wiki/modular-arithmetic

Máme tu akýsi dlhý výpočet a našou úlohou je vypočítať výsledok modulo nejakého čísla (`výsledok % M` vo veľa jazykoch).

_Ak ste zvedavý prečo je modulárna aritmetika tak dôležitá, pozrite si úlohy
[úvod do šifrovania s verejným kľúčom](./public-key-cryptography-intro) a [RSA šifrovanie](./rsa-cryptography)._

**Vstupné** dáta budú mať:

- počiatočné číslo v prvom riadku;
- jeden alebo viac riadkov popisujúci operácie, vo forme `znak a hodnota` kde znak je buď `+` alebo `*` a hodnota je celé číslo;
- posledný riadok je v rovnakej forme ale so znakom `%` a čísla, ktorým by mal byť výsledok vydelený aby sme dostali zvyšok.

**Odpoveď** by mal byť zvyšok výsledku vydelený posledným číslom, po vykonaní všetkých operácií postupne (počnúc začínajúcim číslom).

_Ak máte problémy s touto úlohou, neváhajte napísať názov úlohy do "vyhľadávacieho" poľa na vrchu v menu a nájdete relevantné
témy na našom fóru._

Príklad:

	vstupné dáta:
	5
	+ 3
	* 7
	+ 10
	* 2
	* 3
	+ 1
	% 11
	
	odpoveď:
	1

_V tomto prípade je výsledok po vykonaní všetkých operácií `397`_.

Všetky čísla nepresiahnu 10000 (aj keď medzivýsledky môžu byť veľmi veľké).
