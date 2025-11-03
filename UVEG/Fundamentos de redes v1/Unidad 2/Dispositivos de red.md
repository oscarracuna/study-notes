
## Definición de dispositivo
Un dispositivo es un equipo tecnológico que conecta segmentos de red.
Los dispositivos están divididos en dos categorías generales: dispositivos de usuario final y dispositivos de red.

## Dispositivos de usuario final
Los dispositivos de usuario final proveen servicios a un usuario final, por ejemplo: computadoras, escáneres e impresoras.
Los dispositivos de usuario final que proveen una conexión a la red son llamados hosts.

## Dispositivos de red
Los dispositivos de red son todos aquellos que conectan a los dispositivos de usuario final a la red, tales como los [[repetidores]], [[hubs]], [[puentes]], [[switch]]es y [[router]]s.

## Dispositivos de la capa física
- Repetidores
	- Su objetivo es regenerar y resincronizar las señales al nivel de bits para permitir que viajen largas distancias. 
	  ![[Pasted image 20240714153236.png]]
- Hubs:
	- Además de resincronizar y regenerar señales, funcionan como un punto central de conexión para varios hosts.
	  ![[Pasted image 20240714153447.png]]

## Dispositivos de la capa de enlace de datos
- Tarjeta de interface de red ([[NIC]])
	- Network Interface Card.
	- Provee una conexión física a la red para un host.
	- Toda NIC y dispositivo de red tienen asignados una [[MAC]] (Media Access Control).![[Pasted image 20240714153931.png]]
- Puentes
	- Su propósito es filtrar el tráfico en una LAN, la cual hace que se mantenga un tráfico en un segmento, pero a la vez se puede comunicar con otro. 
	- Los puentes filtran el tráfico de la red a través de la dirección MAC.![[Pasted image 20240714154052.png]]
- Switches
	- Son más rápidos que los hubs que realizan una conmutación en software. 
	- Cada puerto de un switch actúa como un puente separado.![[Pasted image 20240714154320.png]]

## Dispositivos de la capa de red
- Routers
	- Es un dispositivo de la capa de red que pasa paquetes de datos entre redes, todo esto basándose en un direccionamiento lógico.
	- Además, toman decisiones acerca de la mejor ruta para entregar paquetes en la red.
	- Estos pueden conectar diferentes tecnologías de la capa de enlace de datos.
	- Son la columna vertebral del internet.![[Pasted image 20240714154828.png]]

## Dispositivos de capas superiores
- [[Firewalls]]
	- Protege los recursos de una red de los usuarios de otras redes, ya que el firewall examina los paquetes de la red y determina si es seguro que los datos entren o salgan de la red.
	- Puede ser tanto un software o hardware.