Apliquemos nuestras habilidades de programación a un problema cuasi científico - ya que es un poco 
aburrido sólo aprender cosas abstractas.

Una forma simple de medir el tipo de cuerpo fue propuesta en la mitad del siglo XIX. Sólo depende de la altura 
y peso de una persona, y se llama **Índice de Masa Corporal** o **BMI**, por sus siglas en inglés. Se define como:

    BMI = peso / altura^2

Donde el peso es calculado en `kilogramos` y la altura en `metros`.

Se proponen cuatro notas generales:

    Bajo peso (Underweight)      -           BMI < 18.5
    Peso normal (Normal weight)  -   18.5 <= BMI < 25.0
    Sobrepeso (Overweight)       -   25.0 <= BMI < 30.0
    Obesidad (Obesity)           -   30.0 <= BMI

Por ejemplo, si tengo un peso de `80 kg` y una altura de `1.73 m` puedo calcular:

    BMI = 80 / (1.73)^2 = 26.7

En otras palabras, algo de sobrepeso.

No discutiremos qué tan apropiadas son estas notas. En vez de esto, sólo debes calcular notas para varias personas.

**Datos de entrada**: Contienen el número de personas en la primera línea.  
Cada otra línea contiene dos valores - peso en kilogramos y altura en metros.  
**Respuesta**: Debe contener palabras `under`, `normal`, `over`, y `obese` para cada caso correspondiente, 
separadas por espacios. Por ejemplo:

    datos de entrada:
    3
    80 1.73
    55 1.58
    49 1.91

    respuesta:
    over normal under
