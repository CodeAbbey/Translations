Rotar la cadena de caracteres en ´K' significa cortar esos caracteres desde el inicio y transferirlos al final de la cadena.
Si 'K' es negativo, los caracteres al contrario deben ser transferidos desde el final hasta el inicio.

**Datos de entrada** contendran el numero te casos de prueba en la primera linea.
Las siguientes lineas contendran el numero 'K' y alguna cadena 'S' separada por espacio- un par en cada linea.
La cadena 'S' contendra unicamente letras en minusculas. 'K' no excederá la mitad de la longitud de 'S' en valor absoluto.
**Respuesta** debe contener cadenas rotadas de acuerdo con la regla anteriormente dada, separadas por espacios. Por ejemplo:

    datos de entrada:
	2
	3 forwhomthebelltolls
	-6 verycomplexnumber
	
	respuesta:
	whomthebelltollsfor numberverycomplex

La tarea podria ser facilmente resuelta creando una nueva clase de cadena concatenando las dos subcadenas.
Sin embargo, si quieres un desafio más serio, te puedes animar a desarrollar la rotación "en campo", moviendo los bytes de
la cadena original (Es decir, sin pedir memoria para nuevos datos). Esto podria ser hecho con la ayuda de un loop y solo con 
una variable temporal.
