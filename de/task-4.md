<div class="text-center">
	<img src="http://s5.postimg.org/j3mtrsuk7/min_of_two.gif" alt="Kleinstes wählen Animation"/>
</div>

Oft müssen Programme Entscheidungen zum Ablauf eines Programms wählen. Darum werden wir jetzt etwas "Bedingte Anweisungen und Verzweigungen" üben. 
Üblicherweise wird das mit Hilfe des `if ... else` statements geschehen, das wie folgt aussieht:

    IF irgendeine_aussage THEN
	    tu_dies
	ELSE
	    tu_was_anderes
	ENDIF

Abhängig von Ihrer gewählten Programmiersprache kann die Syntax etwas davon abweichen und der `else` Teil ist fast immer nur optional. 
Im Wikipedia Artikel über [Bedingte Anweisung und Verzweigung][cond] können Sie mehr darüber nachlesen.

[cond]: https://de.wikipedia.org/wiki/Bedingte_Anweisung_und_Verzweigung

Gegeben sind zwei Zahlen von denen Sie jeweils immer die kleinste Zahl als Lösung wählen. Insg. stehen aber mehrere Zahlenpaare zur Verarbeitung bereit. 

**Eingabe Daten** enthält in der ersten Zeile die Anzahl der zur Verarbeitung anstehenden Zahlenpaare.  
Die nachfolgenden Zeilen enthalten die Zahlenpaare, dessen Elemente es zu vergleichen gilt.  
Als **Lösung** geben Sie bitte stets das kleinste Element durch Leerzeichen getrennt an. Zum Beispiel:

    Daten:
	3
    5 3
    2 8
    100 15
    
    Lösung:
    3 2 15
