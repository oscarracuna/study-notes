
# **Estructuras selectivas**
Se utilizan para la toma de decisiones lógicas binarias (0 y 1) y se basan en el uso de una o más condiciones (if, else, elif).
La condición se evalúa y dependiendo del resultado se ejecuta una u otra acción, pero *nunca ambas a la vez*.

**if**
```java
if (condicion) {
	// 
}
```
**if-else**
```java
if (condicion) {
	// if true
} else {
	// if false
}
```
**if-else-if**
```java
if (condicion) {
	// if ture
} else if (condicion) {
	
} else if (condicion) {

} else {

}
```
**if else if else**
```java
if (condicion) {
	if (condicion) {
	}
} else {
	if (condicion) {
	} else{
	}
}
```
**if else anidados**
- Las instrucciones pueden anidarse para hacer múltiples validaciones.

**Instrucciones switch**
```java
switch (valor) {
	case 'caso_1': {
		// Se ejecuta el caso 1
		break;
	},
	case 'caso_2': {
		// Se ejecuta el caso 2
		break;
	}
	...
	default:
		// En caso de no encontrar
		// coincidencia, se ejecuta este caso
		break;
}
```
**Ejemplo**
```java
String mes = 'febrero';
switch (mes) {
	case 'enero':
		// Cuando mes es igual a enero
		break;
	case 'febrero':
		// Cuando mes es igual a febrero
		break;
	case 'marzo':
		// Cuando mes es igual a marzo
		break;
	default:
}
```
Si mes = febrero, entramos en caso febrero.
De no ser así, caemos en default.


## **Estructuras iterativas (bucles, loops)**
Secuencia de instrucciones de código que pueden repetirse un número de veces, delimitado por una condición.
```java
for (inicializacion; condicion; actualizacion) {
	// sentencia a ejecutar
}
```
- Inicialización
	- Declaración e inicialización de las variables.
- Condición
	- Condición a ser evaluada en cada iteración.
- Actualización
	- Modificación de la variable que debe cumplir con la condición.

```java
while (condicion){

}
```
```java
do {

} while (condicion);
```

**Recursividad**
Técnica en la cual un método se manda llamar a sí mismo en algún momento de su ejecución.

```java
/* 
imprimirValor (valor)
	mostrar(valor);
si valor es menor a 10
	llamar imprimirValor(valor + 1)
en caso contrario
	terminar
*/

public class Recursividad {
	public static void main(String []args) {
		metodo_revursivo(1);
	}

	static void metodo_recursivo(int valor) {
		if (valor < 10) {
			System.out.println("valor: " + valor);
			metodo_recursivo(valor + 1);
		} else {
			System.out.println("Fin metodo recursivo");
		}
	}
}
```

