
**Elementos de un lenguaje de programación: Java**

[[Identificadores]]
- Los identificadores son los nombres con los que el programador designa a los paquetes, las clases, las variables, las constantes y los métodos de un paquete.
	- Dígitos y letras
	- _ y $ son permitidos
	- No deben iniciar con dígitos
	- No debe tener caracteres especiales
	- No debe ser una palabra reservada
- Ejemplos de identificadores válidos:
	- `nombre`
	- `Nombre`
	- `numero1`
	- `_genero`
	- `$cantidad`
- Identificadores no válidos:
	- `1numero`
	- #edad
	- `a+b`
	- `public`

**[[Variables]]**
Lugar de memoria donde se puede almacenar información del tipo que el programador elija (Se almacena en la RAM).
Se le conocen como variables porque su valor puede ir cambiando mientras se va ejecutando.
Ejemplo:
	`int edad = 30;`

**[[Variables de clase]]**
Variables cuyo valor es el mismo para la clase y para todas sus instancias. (public static main and all of those)

**[[Variables locales]]**
Son variables declaradas dentro de un método. Se crean cuando el bloque inicia y se destruyen cuando finaliza la ejecución de dicho bloque. Por ejemplo, variables en una función no se pueden utilizar en otra.

```java
class Suma {
	static int a = 50;
	
	public static void main (String [] args) {
		int b = 30, resultado = 0;
		resultado = a + b;
		System.out.println("El resultado es: " + resultado);
		}
}
```

**[[Constantes]]**
Lugar de memoria donde se puede almacenar información.
Su valor no puede cambiar durante toda la ejecución del programa.
La palabra reservada 'final' se utiliza para declarar constantes.
Por convención, las constantes se declaran en mayúsculas.
Ejemplo
	`final double  PI = 3.1416;`

**[[Operadores]]**
- Aritméticos
	- `+ suma
	- `- resta
	- `* multip`
	- `/ division`
	- `% Modulo o el sobrante de una division`
- Racionales
	- < menor que
	- > mayor que
	- <= menor o igual que
	- >= mayor o igual que
	- != inecuacion o distinto 
	- == igual que
- Unitarios
	- && o & 
		- El resultado será true si ambos son true y false si no
	- || o | 
		- El resultado será false si ambos operandos son false y true si no
	- ! 
		- Si el operando es true, el resultado es false y si el operando es false, el resultado es true
	- ^ 
		- El resultado será true si un operando es true y el otro false, y false en  caso contrario.
- Lógicos
	- ~ Complemento A1
	- - Cambio de signo del operando
	- -- Decremento
	- ++ Incremento
- Asignación
	- `- Asignación
	- `+= Suma y asignación
	- `-= Resta y asignación
	- `*= Mult y asignación
	- `/= División y asignación
	- `%= Módulo y asignación
- 