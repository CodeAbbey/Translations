<!-- #Eine lineare Funktion -->
Ein häufiges Problem bei der Computerprogrammierung besteht darin, das einem bestimmten Phänomen zugrunde liegende Gesetz zu bestimmen.
Aus Lernzwecken wollen wir eine einfache Variante üben - die Entdeckung der linearen Abhängigkeit durch zwei gegebene Beobachtungen (zum Beispiel, wie der Preis
für ein Produkt von seiner Größe, seinem Gewicht usw. abhängt)

Eine lineare Funktion wird durch eine Gleichung definiert, bei der `a` und `b` Konstanten sind:

    y(x) = ax + b
 
Als Beispiel, mit `a=3, b=2` erzeugt die Funktion die Werte `y = 2, 5, 8, 11...`  
für `x = 0, 1, 2, 3...`

Ihre Aufgabe ist es, `a` und `b` mithilfe von zwei Punkten zu bestimmen, die zur Funktion gehören.  
D.h. Sie erhalten zwei Paare mit Werten `(x1, y1), (x2, y2)`, die die Funktionsgleichung erfüllen - und sollen die Gleichung selbst wiederherstellen.

**Eingabe Daten** enthalten die Anzahl der Testfälle in der ersten Zeile  
und dann die Testfälle selbst in einzelnen Zeilen.  
Jeder Testfall besteht aus `4` Ganzzahlen (`x1 y1 x2 y2`).  
Die **Antwort** sollte ebenfalls aus ganzzahligen Paaren bestehen, die jeweils in einer Zeile mit Leerzeichen getrennt und von Klammern umschlossen sind, als Beispiel:

    Eingabe Daten:
    2
    0 0 1 1
    1 0 0 1
    
    Antwort:
    (1 0) (-1 1)
