Este problema introduce el popular algoritmo de "búsqueda lineal", el cual debe ser aprendido completamente ya que es frecuentemente
usado en la programación de tareas más complejas (ordenamiento, etc.)

Una operación muy común en una secuencia de valores, o vectores, es la de encontrar su valor extremo - máximo o mínimo. Para lograrlo,
se necesita almacenar el **máximo actual** (o mínimo, según sea el caso) en una variable separada, y luego recorrer el vector,
comparando cada uno de sus elementos con esta variable. Cuando el siguiente valor sea mayor que esta variable temporal, este
valor debería ser copiado a ella (como un nuevo máximo).

Al final del recorrido, esta variable temporal portará el valor extremo.

Los **Datos de entrada** te darán exactamente `300` números en una sola línea.  
La **Respuesta** debería contener el máximo y el mínimo de estos valores, separados por espacios.

Ejemplo:

    datos de entrada:
    1 3 5 7 9 11 ... 295 297 299 300 298 296 ... 12 10 8 6 4 2

    respuesta:
    300 1

