Cuando los programas procesan números que tienen una parte decimal, algunas veces queremos **redondear** tales valores a números enteros. Necesitaremos esto para programar algunos problemas posteriores (por ejemplo, para hacer las respuestas más sencillas), así que
dediquemos el siguiente ejercicio a aprender este truco.

Hay varios pares de números. Para cada par, dividirás el primer número entre el segundo y mostrarás el resultado redondeado al entero **más cercano**.

En ciertos casos, cuando el resultado contenga exactamente `0.5` como parte decimal, el valor debería ser redondeado hacia arriba
(ej.: sumando otro `0.5`). Nota que para valores negativos, "mayor que" quiere decir
"más cercano a cero". Revisa la página de Wikipedia sobre [Redondeo](https://es.wikipedia.org/wiki/Redondeo)
para explicación más detallada.

En cualquier problema posterior, cuando se mencione redondeo - se asume que es el mismo
algoritmo de redondeo (a menos que explícitamente se especifique otro).

Los **Datos de entrada** darán un número de casos en la primera línea.  
Cada una de las siguientes líneas contendrá un caso de prueba (ej.: un par de números).  
La **Respuesta** debería contener los resultados divididos y redondeados para cada par, separados por espacios.

Ejemplo:

	datos de entrada:
	3
	12 8
	11 -3
	400 5
	
	respuesta:
	2 -4 80
