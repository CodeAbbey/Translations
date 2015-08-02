Un problema muy común en la programación computacional es determinar la ley subyacente a la cual un fenómeno obedece. Para propósitos de aprendizaje, practiquemos una variante sencilla - descubrir la dependencia lineal de dos observaciones dadas (por
ejemplo, cómo el precio de un producto depende de su tamaño, peso, etc.)

Una función lineal está definida por la ecuación:

    y(x) = ax + b

Donde `a` y `b` son unas constantes.  
Por ejemplo, con `a=3, b=2` la función arrojará los valores `y = 2, 5, 8, 11...` cuando `x = 0, 1, 2, 3...`

Tu tarea es determinar `a` y `b` usando dos puntos que pertenecen a la función, ej.: Se te indican dos pares de valores `(x1, y1), (x2, y2)` los cuales satisfacen la ecuación de la función - y deberás restaurar la ecuación en sí.

Los **Datos en entrada** tienen el número de casos de prueba en la primera línea y luego, en líneas separadas, los casos en sí.  
Cada caso contiene `4` enteros (`x1 y1 x2 y2`).  
Las **Respuestas** deberían ser enteros también y deben escribirse en una línea, separadas con espacios y encerrando cada par en paréntesis, por ejemplo:

    datos de entrada:
    2
    0 0 1 1
    1 0 0 1
    
    respuesta:
    (1 0) (-1 1)
