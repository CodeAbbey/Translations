Este problema proporciona un ejercicio para el aprendizaje de la idea centra del infame algoritmo de ordenación - [ordenación por burbuja](./bubble-sort) - el cual
se estudiará un poco más tarde.

Dado un vector de enteros, necesitaremos iterar sobre todas las parejas de elementos vecinos, empezando por el principio - 
e intercambiando los miembros de cada pareja, cuando el primero sea mayor que el segundo.

Por ejemplo, consideremos un pequeño vector con los elementos `1 4 3 2 6 5`, y marquemos las parejas que se intercambiarán y cuales no:

	(1  4) 3  2  6  5  - permanece igual
	1 (4  3) 2  6  5  - intercambio
	1  3 (4  2) 6  5  - intercambio
	1  3  2 (4  6) 5  - permanece igual
	1  3  2  4 (6  5) - intercambio
	1  3  2  4  5  6  - permanece igual

Esta operación mueve los elementos mayores hacia la derecha, hacia el final del vector, y los elementos más pequeños hacia la izquierda
(hacia el principio).
Lo que es más importante: **el elemento más grande acabará en la última posición**.

**Datos de entrada** contienen la secuencia de elementos del vector, todos positivos. Después el valor `-1` indica el final
(por tanto, no debe ser incluido en el vector).
**Respuesta** debe contener dos valores - el numero de intercambios efectuados y la suma de comprobación de dicho vector
después de procesado (separados por espacios).  
La suma de comprobación debe ser calculada con el mismo método usado en
la tarea [Suma de comprobación de un vector](./array-checksum)

Ejemplo:

	Datos de ENtrada:
	1 4 3 2 6 5 -1
	
	Respuesta:
	3 5242536
