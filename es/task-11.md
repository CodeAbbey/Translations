Este ejercicio de programación tiene como propósito darte una introducción a los aspectos básicos de un sistema de numeración. Comencemos a aprender
este concepto experimentando con el sistema decimal que usamos cotidianamente (aunque deberías tener presente que el computador no lo
usa internamente - sólo convierte números a él cuando tiene que mostrarlos al usuario).

Como cualquier número mayor a 9 es representado por varios dígitos, podemos calcular la suma de estos dígitos. Por ejemplo,
para los números `1492` y `1776` tenemos:

    1 + 4 + 9 + 2 = 16
    1 + 7 + 7 + 6 = 21

En esta tarea se te darán varios números y se te pedirá que calcules las sumas de sus dígitos.  

**Importante:** Aunque muchos lenguajes de programación tienen funciones incorporadas para convertir números a cadenas
(desde las cuales los dígitos pueden ser obtenidos), no deberías usarlas (ya que tu objetivo es aprender algunos trucos de programación).

**En su lugar**, debes implementar un algoritmo con división repetitiva entre 10 (la base del sistema numérico) y sumar sus
residuos. Lee el artículo [Number to digits][numtodig] para más detalles sobre el algoritmo.

[numtodig]: ../wiki/number-to-digits

###Enunciado del problema

Los **Datos de entrada** están en el siguiente formato:

- la primera línea contiene `N` - el número de valores a procesar;
- y después siguen `N` líneas que describen los valores para los cuales la suma de dígitos debe ser calculada mediante `3` enteros `A B C`;
- para cada caso, necesitarás multiplicar `A` por `B` y sumar `C` (ej.: `A * B + C`) - luego calcular la suma de dígitos del resultado.

La **Respuesta** debería constar de `N` resultados, separados también por espacios. Por ejemplo:

    datos de entrada:
    3
    11 9 1
    14 90 232
    111 15 111
    
    respuesta:
    1 16 21

Aquí el primer caso requiere calcular `11*9+1 = 100` y la suma de sus dígitos es `1+0+0 = 1`.
