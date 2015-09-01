Lassen Sie uns nun unsere Programmier-Kenntnisse an einem "quasi" Wissenschaftlichen Problem anwenden. 
Schliesslich ist es ein bisschen langweilig nur abstrakte/theoretische Dinge zu erlernen. 

Die einfache Messung der Körperkonstitution wurde in der Mitte des XIX Jahrhunderts vorgeschlagen.
Es basiert einzig auf Körpergroße und Gewicht einer Person und wird **Body Mass Index** oder auch **BMI** genannt.
Es ist definiert als:

    BMI = Gesicht / Körpergröße^2

Wobei Gewicht in `Kilogram` und Körpergröße in `Meter` gemessen wird.

Generell unterscheided man Vier Grade:

    Untergewichtig     -           BMI < 18.5
    Normalgewichtig    -   18.5 <= BMI < 25.0
    Übergewichtig      -   25.0 <= BMI < 30.0
    Fettleibig         -   30.0 <= BMI

Als Beispiel, bei einem Gewicht von `80 kg` und einer Körpergroße von `1.73 m` berechnet sich mein BMI wie folgt:

    BMI = 80 / (1.73)^2 = 26.7

Bin in sofern etwas übergewichtig.

Wir werden nun nicht darüber diskutieren wie ungenau und unangemessen diese Einteilung ist. 
Statt desen sollen Sie einfach nur die BMI Stufen für mehrere Personen berechnen und ausgeben. 

**Eingabe Daten** enthält in der ersten Zeile die Anzahl der Personen für welche Sie den BMI Grad berechnen sollen.  
Die nachfolgenden Zeilen enthalten jeweils zwei Werte - Das Gewicht in KG und die Körpergröße in Meter.  
**Lösung** sollte in einer Zeile durch Leerzeichen getrennt die BMI Stufe als "Wort" ausgeben.  
Verwenden Sie dazu bitte die englische Bezeichnungen `under`, `normal`, `over` oder `obese` entsprechend der BMI Grade.

Beispiel:

    Eingabe Daten:
    3
    80 1.73
    55 1.58
    49 1.91

    Lösung:
    over normal under
