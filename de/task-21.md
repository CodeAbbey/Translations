<!-- #Array von Zählern -->

Anhand dieses Problems lernen wir einen beliebten Programmiertrick, der in vielen Varianten der statistischen Berechnungen verwendet wird.

Stellen Sie sich vor, dass ein Förster versucht, Kiefern, Tannen und Birken in einem bestimmten Waldstück zu zählen. Er kann diesen Abschnitt dreimal durchgehen und beim ersten Durchgang nur Kiefern, beim zweiten nur Tannen und beim dritten nur Birken zählen. 

Effizienter ist es allerdings nur einmal durch das Waldstück zu gehen und für jeden Baum einen Punkt auf einer der Baumseiten in seinem
Notizbuch zu machen - die erste Seite für Kiefern, die nächste für Tannen und die letzte für Birken. Das ist die Idee des Zählens ähnlicher Elemente in einer Sequenz, 
mithilfe einer Reihe von Zählern (hier einem Array statt eines Notizbuches).

Wir bekommen ein Array der Länge `M` mit Zahlen im Bereich von `1 ... N`, wobei `N` kleiner oder gleich `20` ist.
Wir werden es durchlaufen und zählen wie oft jede Zahl vorkommt.  
D.h. es ist eine ähnliche Aufgabe wie [Vokale Zählen](./vowel-count), allerdings müssen wir mehr als einen Zähler verwalten. Achten Sie darauf, 
dass Sie ein eigenes Array für die Zähler verwenden anstatt viele seperate Variablen für jeden Zähler zu erstellen.

Die **Eingabe Daten** enthalten `M` und `N` in der ersten Zeile.  
Die zweite (ziemlich lange) Zeile wird `M` mithilfe von Leerzeichen getrennte Zahlen enthalten.  
Die **Antwort** soll genau `N` durch Leerzeichen getrennte Werte beinhalten. Die erste Zahl soll die Anzahl der `1`-sen,
die zweite die Anzahl der `2`-en entsprechen - und so weiter.

Beispiel:

    Eingabe Daten:
    10 3
    3 2 1 2 3 1 1 1 1 3

    Antwort:
    5 2 3
