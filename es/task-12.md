El manejo de los residuos puede convertirse en un gran dolor de cabeza para los programadores novatos. Escribamos un programa sencillo que
gire en torno a esta operación, con el fin de estudiar de mejor manera la división de enteros. Al mismo tiempo, tendremos algo de práctica
en la manipulación de fechas - las cuales algunas veces dan dolores de cabeza hasta a codificadores/programadores experimentados.


En aritmética, el residuo (o módulo) es la cantidad "que queda" después de realizar la división de dos enteros
que no se dividen exactamente (extraído de la [Wiki][wiki]). Esta tarea proporcionará más práctica aún con la operación módulo.

[wiki]: https://es.wikipedia.org/wiki/Resto

Supongamos que se nos dan dos fechas - por ejemplo, cuando el tren o el barco transbordador inician su viaje y cuando lo termina. Estas fechas lucen así:

    inicio: May 3, 17:08:30
    fin  : May 8, 12:54:15

y tenemos la curiosidad de saber cuánto tiempo (en día, horas, minutos y segundos) se gasta en viajar (quizá con el fin de
escoger la opción más rápida). ¿Cómo podríamos lograrlo?

Una de las maneras más fáciles es:

- convierte ambas fechas a números grandes, representando los segundos desde el inicio del mes (o año, o siglo);
- calcula sus diferencias - ej.: tiempo de viaje en segundos;
- convierte esta diferencia de nuevo a días, horas, minutos y segundos.

La primera operación podría ser realizada multiplicando los minutos por `60` y las horas por `60*60`, etc. y sumando todos los valores que resulten.  
La tercera operación debería ser realizada a lo contrario, mediante varias divisiones que preserven los residuos.

En esta tarea se nos dan varios pares de fechas. Supongamos que ambas fechas del par corresponden siempre al
mismo mes, por lo que sólo se nos dará el número de días. Queremos calcular la diferencia entre las fechas de cada par.

**Datos de entrada:** La primera línea contiene el número de casos; las otras contienen los casos de prueba en sí.  
Cada caso de prueba contiene `8` números, `4` por cada fecha: `día1 hora1 min1 seg1 día2 hora2 min2 seg2` (la segunda fecha siempre
será posterior a la primera).  
**Respuesta:** Para cada caso, deberás mostrar la diferencia como sigue `(días horas minutos segundos)` - por favor,
no olvides los paréntesis - y separados por espacios.

Ejemplo:

    datos de entrada:
    3
    1 0 0 0 2 3 4 5
    5 3 23 22 24 4 20 45
    8 4 6 47 9 11 51 13

    respuesta:
    (1 3 4 5) (19 0 57 23) (1 7 44 26)
