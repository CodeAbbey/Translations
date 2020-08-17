Numeros aleatoreos son a menudo usados en programacion de juegos e investigaciones cientificas, pero también ellos pueden ser útiles incluso
en aplicaciones de negocios (para generar claves unicas, passwords etc.). Nosotros vamos a aprender como son 
generadas y tendremos una practica con algunos metodos simples.

Aqui está uno de los primeros metodos para producir una secuencia de semilla independiente (Es decir numeros seudoaleatoreos):

1. Elige un valor inicial de 4 digitos (Es decir en el rango '0000...9999').
2. multiplicalo por si mismo (Es decir, elevalo a la segunda potencia) para obtener un valor de 8 digitos (añade los ceros - al inicio- faltantes si es necesario).
3. Truncar los dos primeros y dos ultimos digitos en la representación decimal de este resultado.
4. El nuevo valor debe contener 4 digitos y será el siguiente valor de la secuencia.

Ejemplo:

    5761                      - Tomemos este como el primer numero
	5761 * 5761 = 33189121    - elevemoslo al cuadrado
	33(1891)21 => 1891        - truncamos para obtener el medio
	
	1891                      - este es el segundo numero de la potencia
	1891 * 1891 = 3575881    - elevado al cuadrado (y llenando con ceros al inicio para obtener 8 digitos)
	03(5758)81 => 5758         - truncamos para obtener el medio
	
	5758                      - Este es el tercer numero en la secuencia(y así sucesivamente)

Resulta obvio que tarde o temprano cada secuencia llegará a una especie de bucle, por ejemplo:

    0001 -> 0000 -> 0000                   - llega a un bucle despues de dos iteraciones
	4100 -> 8100 -> 6100 -> 2100 -> 4100   - llega a un bucle despues de 4 iteraciones

Te serán dados valores iniciales para varias secuencias. Por cada una de ellas, reporta el numero de iteraciones necesarias
para llegar a la repeticion.

**Datos de entrada** la primera linea, contendrá la cantidad de valores iniciales. La segunda linea contendrá los valores iniciales
separados por espacios.
**Respuesta** debe contener el número de iteraciones para las  secuencias con las cuales dado el valor inicial se convierte en bucle.

Ejemplo:

    datos de entrada:
	3
	0001 4100 5761
	
	respuesta
	2 4 88
* Sugerencia: para truncar el valor de 8 dígitos, divídalo por `100` y luego tome el resto de la división por` 10000`. *
