<!-- #Secuencia de Collatz -->
Este es uno de los problemas matematicos más misteriosos del siglo pasado -- porque su planteamiento es extremadamente simple-
y porque la prueba es aún desconocida. Sin embargo, ofrece un buen ejercicio de programación para novatos.

**Suponga** que selecionamos un valor inicial 'X' y luego construimos una secuencia de valores siguiendo las reglas a continuación:

    si X es par (es decir, X modulo 2 = 0) entonces
	    Xsiguiente = X / 2
	  sino
	    Xnext = 3 * X + 1

Es decir, si `X` es impar, la secuencia crecerá -- y si es par, la secuencia decrecerá. Por ejemplo, con `X = 15` tenemos la secuencia:

    15 46 23 70 35 106 53 160 80 40 20 10 5 16 8 4 2 1
	
Después de que la secuencia alcanza '1' entra en el loop `1 4 2 1 4 2 1...`.

La intriga está en el hecho de que dado cualquier numero inicial 'X' la secuencia tarde o temprano alcanza '1' - sin embargo
imaginate que esta `conjetura de Collatz ` fue expresada en '1937' y hasta el momento nadie ha logrado probar o encontrar un contraejemplo
(Es decir, un numero para el cual la secuencia no termina en '1' --ya sea un entero para el cual el loop es más grande que un loop creciendo hasta infinitamente)
de que la conjetura es para cualquier 'X'.

**Tu tarea**  es que para los numeros dados calcules cuantos pasos son necesarios para llegar a '1'

**Datos de entrada**  en la primera linea contiene el numero de casos a calcular.  
La segunda linea contiene los casos de prueba- Es decir, los valores para los cuales el calculo debe ser hecho.
**Respuesta** debe contener la misma cantidad de resultados, cada una de ellas dando la cuenta del numero de pasos en la secuencia de Collatz
para llegar a ´1´.

Por ejemplo:

  datos de entrada:
	3
	2 15 97
	
	respuesta:
	1 17 118
