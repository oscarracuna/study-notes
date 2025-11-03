[[Sistemas de archivos]]
- Se encargan de administrar el uso de la memoria secundaria en el SO.
- [[Proporcionan acceso a la información]].
	- Deben implementar mecanismos para que las aplicaciones puedan hacer uso de ellos.
- [[Proveen control de acceso]]. 
	- También se encargan de proteger la información. CIA triad.
	- Dar acceso únicamente a usuarios autorizados.

Diferencias entre archivo y directorio
- [[Archivo]]
	- Abstracción que representa una colección de datos con un ID.
	- Tiene un propósito.
	- Posee estructura y nomenclatura.
- [[Directorio]]
	- Contenedor virtual de archivos.
	- Estructura sencilla.
	- Puede soportar otros directorios.
	- Crea estructura jerárquica.
![[Pasted image 20240429193214.png]]
![[Pasted image 20240429193229.png]]

Atributos de archivos
- El sistema de archivos necesita manejar algunos [[metadatos]] asociados, dependiendo de la implementación del sistema de archivos. Los más comunes y generales son:
	- Nombre de archivo.
	- Tamaño real.
	- Información del control de acceso.
	- Ubicación del archivo.
	- Marca de tiempo.
	- Usuario creador.

Operaciones con archivos
- Las operaciones dependen del tipo de archivo, pero las más comunes son:
	- Create
	- Delete
	- Open
	- Read
	- Write
	- Close

Operaciones con directorios
- Al igual que con los archivos, también existen operaciones semejantes para los directorios
	- Create
	- Delete
	- Add file
	- Remove file
	- 
