De este problema aprenderemos un truco popular de programación utilizado en muchas variantes de cálculos estadísticos.

Imagina que un guardia forestal está intentando contar pinos, abetos y abedules en alguna sección del bosque. El guardia puede ir a través de
esta sección en tres ocasiones, contando sólo los pinos en la primera pasada, sólo abetos en la segunda y sólo abedules en la tercera.

Una manera más eficiente es realizar una sola pasada a través del bosque y anotar un punto en una de las tres páginas de su
cuaderno - la primera página es para los pinos, la siguiente para los abetos y la última para los abedules. Esa es la idea para contar elementos similares en una secuencia, utilizando un vector de contadores (en vez del cuaderno). 

Aquí hay una matriz de longitud `M` con números en un rango de `1 ... N`, donde `N` es menor o igual a `20`.
Tenemos que recorrerla y contar cuántas veces se encuentra cada número,
ej.: es similar a la tarea de [contar vocales](./vowel-count), pero necesitamos mantener más de un contador. Asegúrate de
usar un vector separado para ellos, para no crear un montón de variables separadas.

Los **Datos de entrada** contienen `M` y `N` en la primera línea.  
La segunda (y más larga) línea contendrá `M` números separados por espacios.  
La **Respuesta** debería contener exactamente `N` valores, separados por espacios. Primero debería mostrarse la cantidad de `1`,
segundo - la cantidad de `2` y así sucesivamente.

Ejemplo:

    datos de entrada:
    10 3
    1 2 3 2 3 1 1 1 1 3

    respuesta:
    5 2 3
