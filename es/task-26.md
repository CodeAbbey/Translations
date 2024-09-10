<!-- #Máximo Común Divisor -->
Parece que ningún curso de programación para principiantes evita hacer practicar el algoritmo de Euclides para calcular el máximo común divisor de dos números.

El Máximo Común Divisor (MCD) de `a` y `b` es un valor entero `c` tal que tanto `a` como `b` son divisibles por él (es decir, no dejan residuo), y `c` es el valor más grande posible. Por ejemplo, `mcd(20, 35) = 5` y `mcd(13, 28) = 1`. El algoritmo de Euclides es bastante simple: seguimos restando el valor más pequeño (de `a` y `b`) del más grande, repitiendo esta operación hasta que los valores se igualen. Este valor final será el MCD. Para acelerar el proceso, podemos usar la operación de módulo en lugar de la resta.

Por ejemplo:

```
20      35      - restar el primero del segundo
20      15      - restar el mas pequeño del más grande
5       15      - ahora restar el primero del segundo de nuevo
5       5       - una resta mas y aquí está el MCD
```

El Mínimo Común Múltiplo (MCM) de `a` y `b` es un entero `d` que es divisible por ambos (y es el más pequeño de todos los posibles). Se puede encontrar usando la siguiente regla:

```
mcm(a, b) = a * b / mcd(a, b)
```

Por cierto, si este problema te parece demasiado fácil, ¡echa un vistazo a la versión avanzada para encontrar el [MCM de un rango](/index/task_view/lcm-of-a-range)!

### El objetivo:
Los **datos de entrada** contienen el número de casos de prueba en la primera línea. Luego siguen líneas con casos de prueba, cada una conteniendo dos números - `A` y `B`. La **respuesta** debe contener el MCD y el MCM para cada par, rodeados por paréntesis y separados por espacios. Por ejemplo:

```
datos de entrada:
2
2 3
4 10

respuesta:
(1 6) (2 20)
```
translated by Alan Garcia