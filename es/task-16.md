Una rama importante de las matemáticas que usa extensivamente la programación es la estadística - ej.: cálculo de características
de algún conjunto de datos (Piensa en las estadísticas de visitantes/visualizaciones de página del sitio, etc.).
El aprendizaje de esta disciplina se inicia usualmente familiarizándose con el concepto de **valor promedio**.

El valor promedio (o media) de varios números puede ser calculado como su suma dividida por su cantidad. Por ejemplo:

    prom(2, 3, 7) = (2 + 3 + 7) / 3 = 4
    prom(20, 10) = (20 + 10) / 2 = 15

Te serán dados varios vectores, para cada uno de los cuales encontrarás un valor promedio.

Los **Datos de entrada** darán el número de casos de prueba en la primera línea.  
Después seguirán los casos de prueba en sí, un caso por línea.  
Cada caso de prueba describe un vector de números enteros, con el valor `0` señalando su finalización (¡¡¡este cero no debe ser
incluido en los cálculos!!!).  
La **Respuesta** debería contener valores promedios para cada vector, redondeados al entero más cercano (ver la [tarea sobre Redondeo](./rounding)), y separados por espacios.

Ejemplo:

    datos de entrada:
    3
    2 3 7 0
    20 10 0
    1 0

    respuesta:
    4 15 1

