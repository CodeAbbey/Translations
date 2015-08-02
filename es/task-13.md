Este programa se asemeja a algoritmos más complejos usados para la verificación por redundancia cíclica (CRC) y otras sumas de verificación (checksum), y también en funciones hash
para cadenas de caracteres. Por otro lado, te proporcionará un ejercicio más para practicar la separación de valores en dígitos decimales. Quizá
quieras intentar [Sum of Digits](./sum-of-digits) antes de esto.

Calculemos una suma de dígitos, como lo hicimos previamente, pero esta vez multiplicando cada dígito por su posición (contando las posiciones desde la izquierda, y empezando
desde 1). Por ejemplo, dado el valor `1776`, calculamos la suma **ponderada** de sus dígitos (llamémosla "spd") como:

    spd(1776) = 1 * 1 + 7 * 2 + 7 * 3 + 6 * 4 = 60

Los **Datos de entrada** darán el número de casos de prueba en la primera línea.  
Los valores en sí están en la segunda línea. Para cada uno de estos valores vas a calcular su respectiva suma ponderada de dígitos.  
**Respuesta:** Tal como es usual, coloca los resultados en una línea, separándolos con espacios.

Ejemplo:

    datos de entrada:
    3
    9 15 1776

    respuesta:
    9 11 60
