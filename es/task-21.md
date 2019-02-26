En este problema aprenderemos un truco popular de programación, utilizado en muchas variantes de cálculos estadísticos.

Imagina que un guarda forestal está contando pinos, abetos y abedules en alguna zona del bosque. Puede ir a esta zona tres veces, contando sólo los pinos en la primera pasada, sólo abetos en la segunda y sólo abedules en la tercera.

Una manera más eficiente es realizar una sola visita a la zona y anotar un punto en una de las tres páginas de su cuaderno - la primera página es para los pinos, la siguiente para los abetos y la última para los abedules. Esta es la idea para contar elementos similares en una secuencia, utilizando un vector de contadores (en lugar del cuaderno). 

Tenemos una matriz de longitud `M` (zona del bosque) con números (tipos de arboles) en un rango de `1 ... N`, donde `N` es menor o igual a `20`. 
Vamos a recorrerla y contar cuántas veces se encuentra cada número, ej.: es similar a la tarea de [contar vocales - Vowel Count](./vowel-count--es), pero necesitamos mantener más de un contador. Asegúrate de usar un vector separado, para no crear un montón de variables separadas.

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
