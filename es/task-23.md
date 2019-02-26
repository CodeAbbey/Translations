<!-- translation by https://github.com/manlug -->

Este problema plantea un ejercicio para aprender la idea principal del algoritmo de [ordenamiento de burbuja (bubble-sort)](./bubble-sort--es), 
el cual veremos un poco más adelante.

Dada la matriz de enteros, debemos iterar a través de todos los pares de elementos vecinos, comenzando desde el principio, 
e intercambiar los miembros de cada par en el caso de que el primer elemento sea mayor que el segundo.

Por ejemplo, consideremos una pequeña serie de elementos `1 4 3 2 6 5`, marcando qué pares se intercambian y cuáles no:

    (1  4) 3  2  6  5  - pasar al siguiente par
    1 (4  3) 2  6  5   - intercambiar
    1  3 (4  2) 6  5   - intercambiar
    1  3  2 (4  6) 5   - pasar al siguiente par
    1  3  2  4 (6  5)  - intercambiar
    1  3  2  4  5  6   - fin

Esta operación mueve algunos elementos grandes hacia la derecha (hacía el final de la matriz) y algunos elementos más pequeños hacia la izquierda (hacia el principio de la matriz).

Lo más importante es que: **el elemento más grande necesariamente se mueve a la última posición**.

**Datos de entrada** contienen la secuencia de elementos de la matriz, todos positivos. Después de este valor sigue `-1` para marcar el final (que no debe ser incluido en la matriz).

**La respuesta** debe contener dos valores: el número de intercambios realizados y la suma de comprobación (checksum) de la matriz después del proceso realizado (separado por espacios).
La suma de comprobación (Checksum) se debe calcular exactamente con el mismo método que en la tarea
[Suma de comprobación de matriz (Array Checksum)](./array-checksum--es)

Ejemplo:

	Datos entrada:
	1 4 3 2 6 5 -1
	
	Respuesta:
	3 5242536
