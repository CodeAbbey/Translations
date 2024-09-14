<!-- #Área del Triángulo -->
Ser capaz de calcular el área de un triángulo es bastante importante, ya que muchas tareas más complejas a menudo se reducen 
fácilmente a esto (nosotros también lo usaremos más adelante).

Uno de los métodos más antiguos conocidos es la [Fórmula de Herón](https://es.wikipedia.org/wiki/F%C3%B3rmula_de_Her%C3%B3n), que toma como entradas 
las longitudes de los lados del triángulo.

Sin embargo, en este problema debes escribir un programa que utilice las coordenadas `X` e `Y` de los vértices del triángulo en su lugar. 
Así que puedes usar esta fórmula de alguna manera o encontrar otra.

Los **datos de entrada** contendrán el número de triángulos a procesar.
Las siguientes líneas contendrán `6` valores cada una, en el orden `X1 Y1 X2 Y2 X3 Y3`, describiendo los tres vértices de un triángulo.
La **respuesta** debe dar las áreas de los triángulos separadas por espacios (se espera una precisión de aproximadamente `1e-7`).

Ejemplo:

    datos:
    3
    1 3 9 5 6 0
    1 0 0 1 10000 10000
    7886 5954 9953 2425 6250 2108
    
    respuesta:
    17 9999.5 6861563

_translated by [Alan Garcia](/index/user_profile/st-allan)_