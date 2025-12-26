Los [[OS]] se pueden clasificar conforme a cómo estructuran sus componentes (arquitectura), por ejemplo:
- Sistemas monolíticos
- Sistemas de capas
- Microkernels
- Modelo cliente-servidor
- Exokernels
- Máquinas virtuales


[[Sistema monolítico]]
- No tienen estructura definida
- Su estructura es un único programa que integra todo
- Esto garantiza transparencia pero es difícil de manejar
- Por ejemplo:
	- MS DOS
	- Multics
	- OpenBSD
	- FreeBSD
	- Ubuntu
	- Debian
	- Android
![[Pasted image 20240423195259.png]]

Se pueden estructurar de la siguiente manera:
- Programa principal - Llamadas a procedimientos de servicio - llamadas a procedimientos auxiliares
- ![[Pasted image 20240423195528.png]]




[[Sistema de capas]]
- Organización jerárquica
- Dividido en partes más pequeñas
- ![[Pasted image 20240423195748.png]]
- Por ejemplo:
	- THE (Technische Hogeschool Eindhoven) lmfao who????

[[Microkernel]]
- Divide el SO en fracciones muy pequeñas
- Sólo una se ejecuta en modo núcleo (kernel, sudo)
- Si hay errores, estos no detienen o congelan el dispositivo
- El kernel únicamente tiene lo más esencial
	- Abstracción de procesos
	- Admin de hilos
	- Intercomunicación
- ![[Pasted image 20240423200332.png]]
- ![[Pasted image 20240423200356.png]]
- ![[Pasted image 20240423200504.png]]
Ejemplos:
- Híbridos:
	- Windows XP, 7, 8, 10
	- MAC
	- iOS
- MINIX 3
- Symbian


[[Cliente-servidor]]
- Cuenta con dos partes: cliente y servidor
- Se enfoca en redes
- Se enfoca en destinar recursos a la ejecución de programas del cliente
- ![[Pasted image 20240423200737.png]]
- Permite escalabilidad, flexibilidad e interoperabilidad
- Por ejemplo:
	- Cliente
		- Chrome, Firefox, Opera, Edge, Safari
		- SQL Management Studio, MySQL Workbench
	- Servidor
		- Apache, IIS, Nginx
		- SQL Server, MySQL
- ![[Pasted image 20240423201013.png]]


[[Máquina virtual]]
- Poder integrar varios SO en un solo equipo, HOST o hipervisor
- Funciona mediante una réplica del hardware actual
- Se virtualizan los recursos físicos generando réplicas exactas
- A cada [[SO]] le corresponde una copia con recursos reservados
- Ejemplos:
	- Java Virtual Machine
	- Microsoft Hyper-V
- ![[Pasted image 20240423201215.png]]

[[Exokernel]]
- Separa la protección de los recursos de la administración
- En un Kernel normal los programas se comunican con las bibliotecas o kernel
- En un exokernel, los programas se pueden comunicar directamente con el hardware
- ![[Pasted image 20240423201326.png]]
- La idea es disminuir lo más que se puedan las abstracciones
- Ejemplos:
	- MIT AEGIS
	- MIT XOK
		-Se han usado únicamente con fines de investigación