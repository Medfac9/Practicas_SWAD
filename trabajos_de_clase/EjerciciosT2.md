# Tema 2

### Ejercicio 1
Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento (en total 3 elementos en cada subsistema).

![Foto](http://imgur.com/kV9rDfu.jpg)

Web_3 = 97.75% + (1 - 97.75%) * 85% = 99.6625%
Aplication_3 = 99.00% + (1 - 99.00%) * 90% = 99.9%
Database_3 = 99.9999% + (1 - 99.9999%) * 99.9% = 99.9999999%
DNS_3 = 99.96% + (1 - 99.96%) * 98% = 99.9992%
Firewall_3 = 97.75% + (1 - 97.75%) * 85% = 99.6625%
Switch_3 = 99.99% + (1 - 99.99%) * 99% = 99.9999%
Data Center_3 = 99.99% + (1 - 99.99%) * 99.99% = 99.999999%
ISP_3 = 99.75% + (1 - 99.75%) * 95% = 99.9875%

Disponibilidad total 3 = 99.6625% * 99.9% * 99.9999999% * 99.9992% * 99.6625% * 99.9999% * 99.999999% * 99.9875% = 99.21%

### Ejercicio 2
Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad.

Algunos frameworks y librerías para hacer aplicaciones altamente disponibles son: Microsoft Operations Framework ( MOF), IBM High Availability Cluster Multiprocessing y Linux-HA.

### Ejercicio 3

¿Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas y aprender a usarlas.

El nivel de carga de cada uno de los subsistemas en un servidor se puede analizar con programas especializados para ello, los cuales te detallan la sobrecarga de la CPU, de la RAM o del ancho de banda entre otros subsistemas. Algunas herramientas son: el comando Top, Gnome-System-Monitor, Performance Monitor en Windows o Nagios.

### Ejercicio 4
Buscar ejemplos de balanceadores software y hardware (productos comerciales).

* Balanceadores de carga Software:
	* HAProxy
	* Nginx
	* Linux Virtual Servers
* Balanceadores de carga Hardhare:
	* Serie BIG-IP
	* Cisco
	* Load Balancer ADC

Buscar productos comerciales para servidores de aplicaciones.

Algunos productos comerciales para servidores de aplicaciones pueden ser: WebLogic, WebSphere, JBoss AS, Geronimo y TomEE.

Buscar productos comerciales para servidores de almacenamiento.

Algunos productos comerciales para servidores de almacenamiento son: Dell Compellent FS8600 y HP ConvergedSystem 200-HC StoreVirtual System.