<!-- #Rodando los dados -->
Cuando se programa un juego de tablero con dados, muchos programadores novatos experimentan problemas en la conversión de valores aleatoreos
a los valores especificos de los puntos en los dados. La meta de esta tarea es dar una practica en simulacion en rodar dados dados recibiendo valores
de un generador de numeros aleatoreos. 

Supon, que tenemos un generador que nos da valores aleatoreos en un rango entre '0' (incluyendolo) y '1' (sin incluirlo)
esto podria ser encontrado en lenguajes como **Basic**, **Java**, **Matlab** etc.

Queremos convertir esos valores con punto flotante a uno de los seis numeros  **enteros**: entre '1' y'6'. Esto podria ser 
logrado realizando los siguientes pasos:

1. Multiplica el valor aleatoreo por N el cual es el numero de valores que queremos obtener - en nuestro caso multiplicaremos por '6' y 
    el resultado será un valor punto flotante en el rango entre '0' (incluido) y '6' ( no incluido)
2. Ahora tomamos la parte entera del resultado (funcion llamada 'floor' -piso-  o convertir a 'int' -entero-)
    se convertira en uno de los siguientes: `0`, `1`, `2`, `3`, `4`, `5 con la misma probabilidad para cada uno.
3.  Dado que necesitamos valores entre '1' y '6'  nosotros simplemente añadimos '1' al resultado.

Ahora te serán dados varios numeros en el rango `[0 .. 1)` (puedes estar seguro, ellos son provistos por un generador de numeros aleatoreos) -
y tú tienes que convertirlos a valores de dados utilizando el algoritmo de arriba.

**Datos de entrada** En la primera linea contendran el numero total de valores a convertir.
Las siguientes lineas contendran un valor cada una, en forma como `0.142857`.
**Respuesta** deberá contener numeros entre '1' y '6' para cada valor de entrada, producido por el algoritmo mostrado.

Ejemplo:

    6
	0.59558786964
	0.861037873663
	0.385597702116
	0.246237673331
	0.808033385314
	0.0544673665427
	
	respuesta:
	4 6 3 2 5 1
