
Tento problém bol navrhnutý naším kolegom [Andrey 'GlideThestral'](http://www.codeabbey.com/index/user_profile/glidethestral) - ďakujem veľmi pekne za nápad!_

Bola tu úloha [Game of Life](./life-is-simple). Teraz to poďme implementovať pre Intel-4004 CPU emulátor, v
programovacom jazyku assembler. Pred týmto problémom vám odporúčame sa pohrať s [úlohami z assembleru](http://www.codeabbey.com/index/task_list/assembly)
a vedieť ako použiť emulátor atď.

Keďže malé CPU má obmedzené množstvo kódu a dátovej pamäte , poďme sa pozrieť na zjednodušenú verziu hry:

- hráme na poli `8*8`;
- treba vypočítať iba 1 krok;
- hracia plocha má topológiu [toroidnej šachovnice](https://en.wikipedia.org/wiki/Cylinder_chess#Horizontal_Cylinder_chess_and_Toroidal_chess) - ako keby
	boli strany na koncoch zlepené dohromady.

Na vysvetlenie použijeme  `klzák` pohybujúci sa po takejto hracej ploche:

	- - - - - X - -        - - - - - - - -        - - - - - - - -        - - X X X - - -
	- - - - - - X -        - - - - - - - -        - - - - - - - -        - - - - - - - -
	- - - - X X X -        - - - - - - - X        - - - - - - - -        - - - - - - - -
	- - - - - - - -        X - - - - - - -        - - - - - - - -        - - - - - - - -
	- - - - - - - -        X - - - - - X X        - - - - - - - -        - - - - - - - -
	- - - - - - - -        - - - - - - - -        - - X - - - - -        - - - - - - - -
	- - - - - - - -        - - - - - - - -        - - - X - - - -        - - - X - - - -
	- - - - - - - -        - - - - - - - -        - X X X - - - -        - - - - X - - -
		krok 0                 krok 8                 krok 20                krok 24

Takáto topológia nám dovoľuje vyhnúť sa kolíziám s okrajmi - t.j. predstierajme, že takáto plocha
ja kvázi-nekonečná (aj keď veľké konfigurácie zvyčajne skončia kolíziami so sebou).

**Výzva**  
Cieľom je vytvoriť najrýchlejší program na spracovanie `1` kroku hry Game of Life.  
Ako vždy, nekontrolujeme špecifickú odpoveď, ale váš kód v Asm-4004. Bude spustený proti nejakému tajnému
vstupu (rovnaký pre všetkých užívateľov). Nezaberie viac ako `50000` cyklov - a program by nemal prekročiť `256` bajtov.
Nová verzia emulátora dovoľuje výpočet cyklov (sú zobrazené spolu s registrami) - alebo jednoducho zobrazené v
rozhraní nášho [online emulátora](http://www.codeabbey.com/index/wiki/intel-4004-emulator).

_Dvoj-bajtové inštrukcie zaberú dva hodinové cykly. Jedno-bajtové inštrukcie zaberú jeden hodinový cyklus - okrem cyklu `fin`
ktorý tiež zaberá dva._

**Vstup** obsahuje `8` riadkov po `8` znakov, každý - buď `0`  pre prázdnu bunku alebo `1` pre obsadenú bunku. Riadky
sú oddelené jedným znakom nového riadku (taktiež je tu "trailing newline"). Takže vstup pozostáva z `72` znakov.  
**Odpoveď** by tiež mala dávať rovnaké riadky, ale môžu byť oddelené akýmkoľvek znakom, ktorý preferujete (t.j. newline, bodka, pomlčka).

Príklad:

    vstupné dáta:
    01000000
    10100110
    01100111
    00111001
    00000001
    00001000
    00001000
    01100000
    
    odpoveď:
    10000000
    10100100
    00000000
    01111101
    00001000
    00000000
    00010000
    01100000
