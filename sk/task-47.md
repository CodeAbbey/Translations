*Ak si myslíte, že tento problém je pre vás príliš ľahký, vyskúšajte tiež [Prelomenie Cézarovej Šifry!](./caesar-cipher-cracker)*

Kryptografia je jedno z najzaujímavejších odvetví programovania. Učenia sa algoritmov zvyčajne začína s jednoduchou metódou
nazvanou po slávnom Rímskom cisárovi [Júliusovi Cézarovi](https://sk.wikipedia.org/wiki/Gaius_Iulius_Caesar),
ktorý ju používal pre zašifrovanie jeho vojenských tajomstiev
(a možno aj na posielanie zamilovaných listov Kleopatre).

My si v tejto úlohe vyskúšame dešifrovanie zašifrovaných správ.

Princíp algoritmu je jednoduchý. Každé písmeno originálneho textu je nahradené iným, podľa nasledujúceho pravidla:

- nájdite písmeno (ktoré by malo byť zašifrované) v abecede;
- posuňte ho o `K` pozícií ďalej (dole v abecede);
- odtiaľto vezmite nové písmeno;
- ak sa "posúvanie" odohralo na konci algoritmu, pokračujte od začiatku.

Napríklad, ak `K = 3` (hodnota posunu používaná samotným Cézarom), potom sa `A` stane `D`, `B` sa stane `E`, `W` sa stane `Z` a
`Z` sa stane `C` a tak ďalej, podľa nasledujúcej tabuľky:

	A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
	
	| | | | | | | | | | | | | | | | | | | | | | | | | |
	V V V V V V V V V V V V V V V V V V V V V V V V V V 
	
	D E F G H I J K L M N O P Q R S T U V W X Y Z A B C

Takže, ak pôvodná správa bola **VENI VIDI VICI** tak po zašifrovaní dostaneme **YHQL YLGL YLFL**.

Na druhej strane by zašifrovaná správa mala byť "posunutá naspäť" aby mohla byť dekódovaná - alebo posunutá o  `26 - K`, čo je to isté.

Takže ak máme zakódovanú správu **HYHQ BRX EUXWXV**, môžeme použiť posun o `26 - K = 26 - 3 = 23` a získať pôvodnú
správu naspäť, v tomto prípade to bude **EVEN YOU BRUTUS** (AJ TY BRUTUS).


**Vstupné dáta** budú obsahovať 2 celé čísla - počet riadkov zašifrovaného kódu a hodnotu `K`.  
Nasledujúce riadky budú obsahovať zašifrovaný text, pozostávajúci z veľkých latinských písmen `A ... Z`,
každý riadok končí bodkou `.` ktorá by nemala byť dešifrovaná.
**Odpoveď** by mala obsahovať dešifrovanú správu (v jednom riadku, žiadne rozdeľovanie nie je treba).

Príklad:

    vstupné dáta:
	2 3
	YHQL YLGL YLFL.
	HYHQ BRX EUXWXV.
	
	odpoveď:
	VENI VIDI VICI. EVEN YOU BRUTUS.
