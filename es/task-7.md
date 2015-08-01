Este ejercicio de programación es aproximadamente el mismo que contar sumas en bucle (sums in loop), pero necesita unos cuantos cálculos más.

<div class="text-center">
	<img alt="fahrenheit and celsius" src="http://s5.postimg.org/3tpo5bg6v/fahrenheit.png"/>
</div>

*Nota: El problema [Rounding](./rounding--es) explica el algoritmo de redondeo que se usará en esta tarea.*

Hay dos sistemas ampliamente extendidos para medir la temperatura - Celsius y Fahrenheit. El primero es muy popular en Europa
y el segundo es muy usado en los Estados Unidos por ejemplo.

Según la escala de Celsius, el agua se congela a 0 grados y hierve a 100 grados. Según la de Fahrenheit el agua se congela
a 32 grados y hierve a 212 grados. Puedes aprender más en el [artículo de Wikipedia sobre la escala de Fahrenheit][wiki]. Usa estos dos puntos como bases
para la conversión de otras temperaturas.

[wiki]: https://es.wikipedia.org/wiki/Grado_Fahrenheit

Vas a escribir un programa para convertir grados de Fahrenheit a Celsius.

Los **Datos de entrada** contiene `N+1` valores: el primero de ellos es `N` en sí (**Nota** que no deberías intentar convertirlo).  
La **Respuesta** debería contener exactamente `N` resultados, redondeados al entero más cercano y separados por espacios.

Ejemplo:

    datos de entrada:
    5 495 353 168 -39 22
    respuesta:
    257 178 76 -39 -6

*Por favor, ¡date cuenta que el primer `5` no es una temperatura, sino la cantidad de valores a convertir!*
