Esta tarea proporciona práctica en la propiedad fundamental de la operación del residuo en la aritmética - la persistencia del
residuo sobre la adición y la multiplicación. Esta importante propiedad es a menudo usada para verificar los resultados de los
cálculos, en las competencias de programación, en los cálculos de sumas de verificación (checksums) y especialmente para el cifrado.  
Revisa [Modular arithmetic][modar] para una explicación más detallada.

[modar]: ../wiki/modular-arithmetic

Tenemos aquí una especie de cálculo aritmético extenso, y se nos pide el módulo del resultado con otro número (`resultado % M` en varios lenguajes).

_Si tienes curiosidad acerca por qué la aritmética modular es tan importante, puedes darle un vistazo a los ejercicios
[Public Key Cryptography Intro](./public-key-cryptography-intro) y [RSA Cryptography](./rsa-cryptography)._

Los **Datos de entrada** tendrán:

- Número entero inicial en la primera línea;
- Una o más líneas describiendo las operaciones, según el formato `signo valor` donde el signo es `+` o `*` y el valor es un entero;
- La última línea con la misma forma anterior pero con el signo `%` en su lugar, y un número entre el cual el resultado debe ser dividido para obtener el residuo.

La **Respuesta** debería dar el residuo del resultado de todas las operaciones aplicadas secuencialmente (empezando por el número inicial)
y dividido entre el último número.

Ejemplo:

    datos de entrada:
    5
    + 3
    * 7
    + 10
    * 2
    * 3
    + 1
    % 11

    respuesta:
    1

_En este caso, el resultado luego de aplicar todas las operaciones secuencialmente es `397`_.

Ningún número excederá 10000 (aunque los resultados intermedios podrían ser números muy grandes).

