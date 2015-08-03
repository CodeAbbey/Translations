Se nos dan cadenas que contienen `4` tipos de paréntesis - redondo `()`, cuadrado `[]`, rizado `{}` y angular `<>`.
El objetivo es verificar si los paréntesis están en la secuencia correcta, ej.: cualquier paréntesis de apertura debería tener un paréntesis de cierre del mismo tipo en algún lugar posterior de la cadena, y que los pares de paréntesis no deberían superponerse (aunque podrían estar anidados):

	(a+[b*c] - {d/3})  - aquí los paréntesis cuadrados y rizados
	                        están anidados en los redondos
	
	(a+[b*c) - 17]     - aquí los paréntesis cuadrados se superponen
	                        con los redondos, lo cual no tiene sentido

Los **Datos de entrada** contendrán el número de casos de prueba en la primera línea.  
Después seguirá el número especificado de líneas, cada una conteniendo un caso de prueba en forma de una secuencia de caracteres.  
La **Respuesta** debería contener `1` (si el orden de los paréntesis es correcto) o `0` (si es incorrecto) para cada caso de prueba, y separados por espacios.

Ejemplo:

	datos de entrada:
	4
	(a+[b*c]-{d/3})
	(a + [b * c) - 17]
	(((a * x) + [b] * y) + c
	auf(zlo)men [gy<psy>] four{s}
	
	respuesta:
	1 0 0 1

_¡Nota que todos los caracteres que no son paréntesis pueden ser ignorados sin inconvenientes!_
