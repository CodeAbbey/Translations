Muchos problemas matemáticos en programación no son resueltos exactamente, sino aproximadamente, mediante varias computaciones del
resultado, cada de una de las cuales se acerca cada vez más al objetivo.

Practiquemos con el siguiente enfoque el método de cálculo aproximado de la raíz cuadrada:

1. Busca la raíz cuadrada `r` del valor dado `X`.
2. Usa algún valor arbitrario, por ejemplo `r = 1` como la primera aproximación (seguramente no es la más adecuada).
3. Para un cálculo apropiado de la raíz cuadrada, la ecuación `r = X / r` debe cumplirse.
4. Calcula `d = X / r` (d no sería igual a `r`, ya que `r` no es la raíz exacta).
5. Toma el promedio entre `r` y `d` como la nueva aproximación.

Ej.: La fórmula general de cada iteración del cálculo es (`:=` es una asignación):

          r  +  X / r
    r := -------------
               2

Remítete al artículo de [Aproximación de la Raíz Cuadrada](../wiki/square-root-approximation) para más detalles sobre el **Método de Herón**.

Se nos dan entonces valores de `X` para los cuales se realizarán los cálculos y el número de iteraciones `N` a ejecutar.  
Usa `r = 1` al comienzo, y muestra la aproximación resultante (después de las `N` iteraciones).

Los **Datos de entrada** darán el número de casos de prueba en la primera línea.  
Las siguientes líneas contendrán los casos de prueba en sí mismos, cada uno conteniendo un valor `X`, para el cual la raíz cuadrada debería
ser calculada, y `N` - el número de iteraciones de cálculo.  
La **Respuesta** debería contener las aproximaciones calculadas para cada caso, separadas por espacios.

Ejemplo:

    datos de entrada:
    3
    150 0
    5 1
    10 3

    respuesta:
    1 3 3.196

_Los resultados deberían tener una precisión de `1e-7 = 0.0000001` o mejor!_
