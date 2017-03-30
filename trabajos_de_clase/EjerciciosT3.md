# Tema 3

### Ejercicio 1
Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.

En Windows existe un servicio llamado Servicio de enrutamiento y acceso remoto con el que se agrega al servidor gracias a un asistente.
Mientras que en Linux se usa la orden: `route add -net ipDestino/mascara gw enrutador saltos`

### Ejercicio 2
Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el filtrado y bloqueo de paquetes.

En Windows se puede hacer con IPSec. Mientras que en Linux, se puede hacer gracias a la orden iptables, la cual nos permite usar diversas reglas para el filtrado y bloqueo de paquetes.