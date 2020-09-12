_ podria ser util resolver  [Bubble in Array](./bubble-in-arrayarray-es) antes de este problema._

El ordenamiento de arreglos es un problema popular para los recien llegados -- y extremadamente importante en programación profesional
(bases de datos, bibliotecas etc).

**Ordenamiento** es reorganizar acorde a alguna regla simple basada en la comparación. Suponte que tenemos el siguiente arreglo:

    a = [3, 1, 4, 1, 5, 9, 2, 6]

y queremos que sus elementos sean reordenados en un orden no decreciente -Es decir, si un elemento es puesto primero (a la
izquierda) de otro elemento - podemos estar seguros que el primer elemento es menor o igual que el  segundo.

Hablando matematicamente, para algunos indices 'i' y 'j' si 'i<j' entonces `a[i] <= a[j]`.

**Ordenamiento de burbuja ** es uno de los metodos más simples para desarrollar un reordenamiento. Nosotros describiremos esto de manera más simple 
que la usual:

1. Toma un valor de "pase", examinando todos los pares de elementos adyacentes (pares "N-1" para el array de elementos "N").
2. Si para cualquier par con índices `i` e` i + 1` la condición `a [i] <= a [i + 1]` no se cumple, `intercambia` estos dos elementos.
3. Repita dichas pasadas a través de la matriz hasta que la nueva pasada no realice cambios en absoluto.

Resulta obvio, que si el "pase" no desarrolla ningun intercambio, el array está ordenado y los pases futuros no 
cambiarán nada.

Para intercambiar los elementos con indices í´ e ´j´ hay algunas variantes. Por ejemplo la variable temporal 't' puede ser usada:

    t = a[i]
	a[i] = a[j]
	a[j] = t

###Problema

Vamos a implementar la versión descrita del ordenamiento de burbuja. Para testear esto, verificaremos el numero de pases y el numero 
de intercambios hechos antes de que el arreglo esté ordenado.

**Datos de entrada** contendran el tamaño del array en la primera linea y el array en la segunda
(valores enteros separados por espacios).
**Respuesta** debe contener dos valores -  numero de pases desarrollados y el total de numeros de intercabios. Por ejemplo:

    datos de entrada:
	8
	3 1 4 1 5 9 2 6
	
	respuesta:
	5 8

podemos advertir que el numero de intercambios es aproximadamente proporcional a `N^2` donde 'N' es el tamaño del array (promedio es 
cerca de `N^2 / 4`) así que el tiempo que toma el algoritmo crece significativamente más rapido que el numero de datos (por eso es
que este ordenamiento es usado raramente para arrays grandes)


*Información adicional puede ser encontrada en [sorting algorithms comparison](../wiki/sorting-algorithms-comparison)*
