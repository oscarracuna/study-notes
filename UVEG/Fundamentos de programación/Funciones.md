**Declaración de funciones**
Las funciones son un bloque de código (instrucciones), las cuales realizan tareas específicas a las que nombramos mediante su respectivo nombre.

**Estructura de las funciones:**
```java
modificador_de_control_de_accesso tipo_de_dato nombre_del_metodo() {
	//instrucciones

}
```
Ejemplo:
```java
public void metodo() {
	//instrucciones
}

```

**[[Modificadores de control de acceso]]**
Encargado de controlar el acceso, ya sea permitiendo o denegando una función, una variable o una clase.

![[Pasted image 20240526132521.png]]

[[public]]
```java
public class MiClase {

}
```

[[private]]
```java
public class MiClase {
	protected String miVariable = "Variable privada";

	private void mi_funcion_privada() {
	//instrucciones
	}
}
```

[[protected]]
```java
public class MiClase {
	protected String miVariable = "Variable privada"; 
}
```

[[Tipos de datos]]
Son utilizados para definir los valores que pueden tomar las variables. Algunos ejemplos de estos son textos, números enteros, decimales y boleanos. 
	[[Parámetros]]
	Un parámetro es la expansión de la variable a otro ámbito. Los párametros son utilizados para recibir valores que después pueden ser usados para realizar operaciones dentro de una función.
	Para hacer uso de estos [[parámetros]] se envían argumentos, donde un argumento es el valor que se envía.
	Ejemplo:
```java
	public void mi_funcion(String parameter, int parametro_2) {
	//instrucciones
	}
```
![[Pasted image 20240526135357.png]]
![[Pasted image 20240526135446.png]]

**Variables locales y de clase**
[[Variables de clase]] o [[Variables globales]], resultan útiles cuando se quiere tener acceso a una variable en cualquier fragment de código dentro de las clase o del paquete.

Por otro lado, las [[Variables locales]], son declaradas y usadas dentro del bloque de código.

**Retorno de valores**
Las funciones no sólo pueden realizar tareas y quedarse con la información generada, sino que también pueden devolver esos resultados.
Se usa la palabra "return" para indicar que devolverá un valor.

- **Aplicación de retorno de valores**
	- Retornar un entero
	- Retornar un texto
	- Retornar un decimal
	- Retornar un boleado

**Resumen**
![[Pasted image 20240526140351.png]]