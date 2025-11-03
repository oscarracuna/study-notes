[[Memoria]]
- Dispositivo que almacena datos.
- Tiene la función de recordar valores de información para su uso posterior.
- Esta se puede representar como arreglo de palabras (array of strings) o bytes.
- Cada byte tiene una dirección asociada a la cual se puede hacer referencia y usarla posteriormente.
- Existen dos tipos:
	- Memoria física
	- [[Memoria virtual]]

Jerarquía de la memoria
- Jerarquía de 4 niveles (del 0 al 3) con base en tres puntos clave:
	- Velocidad
	- Capacidad (almacenamiento/costo por bit)
	- Coste en base a la capacidad
![[Pasted image 20240428124045.png]]![[Pasted image 20240428124111.png]]
![[Pasted image 20240428124121.png]]
[[Memoria ROM]]
- Read Only Memory.
[[Memoria RWM]]
- Read/Write Memory.


[[Memoria virtual]]
- Es la memoria que necesita cada proceso.
- Esta es utilizada porque en los SO multi programados es inviable mantener todos los procesos cargados en memoria.
- En esta, el sistema operativo simula tener más memoria.
	- --> Se transfieren procesos a la memoria secundaria (disco duro, ssd, etc.).
	![[Pasted image 20240428125600.png]]
	Con memoria virtual:
	![[Pasted image 20240428125634.png]]
	