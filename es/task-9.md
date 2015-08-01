Un triángulo es un objeto compuesto de tres segmentos de recta (los lados del triángulo) conectados en sus extremos.
[El artículo de Wikipedia][wiki] proporciona una explicación más detallada. 

Si tenemos tres segmentos de recta con longitudes `A B C` - hay dos posibilidades: que podamos construir un triángulo con ellos  
(por ejemplo, con `3 4 5` o `3 4 7` - aunque este último tendría un área de cero) o que sea imposible
(por ejemplo `1 2 4`).

[wiki]: https://es.wikipedia.org/wiki/Tri%C3%A1ngulo

Se te dan varios tríos de valores que representan las longitudes de los lados de los triángulos.
Deberías indicar con cuales tríos es posible construir un triángulo y con cuales no lo es.

**Datos de entrada:** La primera línea contendrá el número de tríos.  
Las otras líneas contendrán los tríos en sí (cada uno en una línea separada).  
**Respuesta:** Deberías mostrar `1` o `0` para cada trío (`1` si el triángulo puede ser construido; de lo contrario muestra `0`).

Ejemplo:

    datos de entrada:
    2
    3 4 5
    1 2 4
    
    respuesta:
    1 0
