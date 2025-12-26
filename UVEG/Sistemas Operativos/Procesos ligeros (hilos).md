Arquitecturas clave de los CPU:
- [[Multinúcleo]]
- [[Multiprocesador]]


Multinúcleo
- De un solo circuito integrado o CMP.
- Dos o más *cores*.
- Es la más común.
![[Pasted image 20240428111122.png]]


Multiprocesador
- De dos o más CMP.
- También se le conoce com SMP. (Multiprocesamiento simétrico).
- Se usa mayoritariamente en *mainframes*, súper computadoras o servers
![[Pasted image 20240428111349.png]]

HT Hyperthreading y SMT Simultaneous multithreading.


Multiprocesador vs multinúcleo:
- ![[Pasted image 20240428111657.png]]
- ![[Pasted image 20240428111823.png]]
-  ![[Pasted image 20240428111837.png]]
- ![[Pasted image 20240428111848.png]]
- ![[Pasted image 20240428111905.png]]
- ![[Pasted image 20240428111936.png]]




¿Qué es un [[proceso]]?
- Secuencia de instrucciones o conjunto de acciones
- Todos los procesos contienen un espacio de direcciones y contienen al menos un hilo de ejecución llamado [[hilo principal]].

¿Qué es un [[hilo]]?
- Básicamente son hijos de un proceso pesado.
- Secuencias más pequeñas de instrucciones del programa,
- También conocidos como micro procesos.
- ![[Pasted image 20240428121311.png]]
  ![[Pasted image 20240428121432.png]]
![[Pasted image 20240428121518.png]]

[[Modelo clásico]]
- Se basa en conceptos de [[agrupación de recursos]] y [[ejecución de hilos]].
	- Agrupación de recursos:
		- Un espacio de direcciones.
		- Contiene instrucciones y datos del programa como archivos abiertos por el proceso, procesos hijos, alarmas pendientes, etc.
	- Ejecución de hilos:
		- Este proceso tiene un contador del programa el cual lleva el registro de la instrucción que se va a ejecutar a continuación.

¿Quién decide cómo se ejecutan los procesos?
- El SO. Este determina la prioridad de ejecución, qué proceso va a ser ejecutado y cuál será el siguiente.
- Al momento de que se ejecuta un proceso pesado, también se crea un PCB.
- Por otra parte, los hilos cuentan con TCB (thread control block).
- ![[Pasted image 20240428122258.png]]

[[Estándar POSIX IEEE 1003.1c]]
- Estándar para versiones de hilos en sistemas UNIX.

[[Librerías (API)]]
- Permiten a los desarrolladores de software el manejo de hilos de una manera más sencilla dado que otorgan una interfaz. (Application Programming Interface).
- Estas residen en el espacio del usuario o el espacio brindado por el kernel del SO.

[[API]]
- Conjunto de funciones, métodos, protocolos de comunicación, herramientas, etc., para ser usados como capa de abstracción y ayudar en el desarrollo de software.


Uso e implementación de hilos
- Hilos a nivel usuario (ULT - User Level Threads).
	- ![[Pasted image 20240428122841.png]]
- Hilos a nivel kernel (KLT . Kernel Level Threads).
	- ![[Pasted image 20240428122903.png]]



