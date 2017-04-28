# Tema 5

### Ejercicio 1
Buscar información sobre cómo calcular el número de conexiones por segundo.

Para calcular el número de conexiones por segundo de un servidor podemos usar los benchmark. Los más conocidos son Apache Benchmark, Apache Jmeter, OpenWebLoad y Httperf.

### Ejercicio 2
Revisar los análisis de tráfico que se ofrecen en: http://bit.ly/1g0dkKj

En la captura completa del tráfico de una navegación hacia la página www.bancochile.cl se ha logrado una captura de 891 paquetes durante 61 segundos.

En la captura de pantalla que se puede apreciar en la web del enunciado, se establecen dos zonas de datos principales.
En la primera es la se establece información del N° de Frame, tiempo de la captura, origen, destino, protocolo involucrado y por último un campo de información extra que previamente Wireshark a decodificado.
La segunda zona muestra los datos del Frame capturado entregándonos información de todos los protocolos involucrados en la captura.

### Ejercicio 3
Buscar información sobre características, disponibilidad para diversos SO, etc de herramientas para monitorizar las prestaciones de un servidor.

* Nagios:
	Con ella monitorizamos nuestros servidores (y los servicios que damos en cada uno), gestionamos las alarmas que se puedan generar por caídas o incidencias y llevamos el cómputo de la disponibilidad, parámetro que se usa para medir la calidad del servicio que prestamos.
* Cacti:
	Con esta herramienta podemos monitorizar el estado de nuestra red, por ejemplo, los dispositivos de red o, incluso, visualizar gráficas de la carga de nuestros servidores. Y es que, precisamente, la capacidad de representar gráficas de esta herramienta es lo que más me gusta de ella, porque de un simple vistazo podemos ver la evolución temporal de nuestros sistemas.
* Zabbix:
	Esta herramienta integra las funciones de monitorización y alertas de Nagios junto con la capacidad de visualizar gráficas que nos ofrece Cacti. También es una herramienta en software libre, al igual que Nagios o Cacti, con la que podremos monitorizar nuestros sistemas y equipos.