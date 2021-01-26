# Test FIF Integraciones TLV
Se requiere una funcion en GO que lea una cadena de caracteres la cual contiene multiples campos en el formato TLV y genere un map[string]string con los campos TLV encontrados en la cadena.

## Formato de los campos TLV
Cada campo TLV esta compuesto por 3 partes:

 - **Tipo**: El tipo tiene un largo de 3 caracteres donde el primer caracter indica el tipo de dato  (A: Alfanumérico y N: Numérico) y dos caracteres para indicar el numero de campo Ejemplo: "01" o "15".
 - **Largo**: 2 caracteres que indican el largo del valor, este campo es importante puesto que indica cuantos caracteres leer a continuación.
 - **Valor**: Este es el valor del campo, el cual corresponde al valor del campo, su largo esta determinado por la porción **Largo**.

Ejemplo:

> Para "A0511AB398765UJ1N230200" Los campos son:
> - 05 de tipo Alfanumérico de largo 11 y valor AB398765UJ1
> - 23 de tipo Numérico de largo 2 y valor 00

## Especificaciones
A continuación las especificaciones de la función.
- Debe recibir como argumento un arreglo de bytes el cual contiene el TLV.
- La función retorna 2 valores, el primero es un map con los valores de los campos TLV y el segundo es un error.
- Los escenarios de error son:
	- Si la entrada esta vacia.
	- Si algún campo no cumple con el tipo de  dato especificado.
	- Y cualquier otro caso borde que sea identificado.

## Requisitos
Entregar un repositorio con el código el cual debe cumplir con lo siguiente:
 - Cobertura de 90% del código
 - CI/CD (puedes utilizar cualquier servicio gratuito como travis o circle)
 - Escribir código limpio suma puntos!
 - Incluir un **readme** con instrucciones para compilar, como utilizar y link al CI.

 


