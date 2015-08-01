Cuando hablamos sobre la **progresión aritmética** (o secuencia aritmética) nos referimos a una serie
de números con una propiedad especial - cada valor es seguido por otro que es mayor por una cantidad predefinida (incremento), 
ej.: la diferencia del `(K+1)`-ésimo and `K`-ésimo valor es una constante. A continuación ejemplos de tales secuencias:

	1 2 3 4 5 6 7 ...
	4 6 8 10 12 14 16...
	10 13 16 19 22 25 28...

Dado que la secuencia aritmética puede ser completamente definida por el primer término (`A`) y el valor del
incremento - (`B`), sus primeros términos pueden ser expresados como:

    A + (A + B) + (A + 2B) + (A + 3B) + ...

Vas a calcular la suma de los primeros miembros de la secuencia aritmética.
[El artículo de Wikipedia][wiki] sobre progresión aritmética podría ser de gran ayuda para
quien haya escuchado sobre ella por primera vez.

[wiki]: https://es.wikipedia.org/wiki/Progresi%C3%B3n_aritm%C3%A9tica

**Datos de entrada:** La primera línea contiene el número de casos de prueba.  
Las otras líneas contienen los casos de prueba en forma de tríos de valores `A B N` donde `A` es el primer valor de la secuencia,
`B` es el tamaño del incremento y `N` y es el número de términos que deberían ser calculados.  
**Respuesta:** Muestra los resultados (la suma of `N` términos) de cada secuencia separados por espacios.

Ejemplo:

    datos de entrada:
    2
    5 2 3
    3 0 10
    
    respuesta:
    21 30
