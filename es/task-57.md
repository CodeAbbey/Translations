<div class="text-center">
	<img alt="ejemplo de suavizacion de linea en tabla de datos" src="https://codeabbey.github.io/data/smooth_weather.png"/>
</div>

El pequeño Merlin quiere ser meteorologo. El mide la temperatura del aire cada hora así que despues de 
varios dias el tiene una larga secuencia de valores.

Sin embargo, sus instrumentos no son ideales por lo que las mediciones no son exactas--pues aleatoreamente
saltan hacia arriba y hacia abajo algunos grados del valor real.

observando esto, Merlin decide hacer los datos más suaves. Para lograrlo, el solo necesita que cada valor
sea substituido por el promedio de sus dos vecinos. Por ejemplo, si el tiene una secuencia de cinco valores como esta:

    3 5 6 4 5

Entonces el segundo  (i.e. `5`) debe ser sustituido por `(3 + 5 + 6) / 3 = 4.66666666667`,  
el tercero (i.e. `6`) debe ser sustituido por `(5 + 6 + 4) / 3 = 5`,  
el cuarto  (i.e. `4`) debe ser sustituido por `(6 + 4 + 5) / 3 = 5`.  
Por convencion, los valores primero y ultimo permanecerán iguales.

En la imagen de arriba la linea azul muestra los datos sin procesar, mientras que la roja los muestras suavizados.

Tienes que escribir un programa que le ayude al pequeño Merlin con este algoritmo de procesamiento digital de señales.

**Datos de entrada** En esta primera linea, se dará la longitud de la secuencia de datos de la segunda linea.  
La segunda linea contendra las mediciones.
**Respuesta** debe contener la secuencia procesada. Todos los valores deben ser calculados con una precision minima de `1e-7`.

Ejemplo:

    datos de entrada:
	7
	32.6 31.2 35.2 37.4 44.9 42.1 44.1
	
	respuesta:
	32.6 33 34.6 39.1666666667 41.4666666667 43.7 44.1
