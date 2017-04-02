# Práctica 3

En la tarea uno, se pide configurar una máquina e instalarle el nginx como balanceador de carga. Para ello, ejecutamos estas tres instrucciones:  
`sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get autoremove`  
`sudo apt-get install nginx`  
`sudo systemctl start nginx`  
Una vez insstalado nginx, configuramos el fichero `/etc/nginx/conf.d/default.conf` con la siguiente información.

![Captura 1](http://imgur.com/lYuvkpr.jpg "Configuración nginx")

![Captura 2](http://imgur.com/YeubPh2.jpg "Prueba nginx sin weight")

Como se puede apreciar, por defecto, el tráfico se dibide por igual para cada máquina, para distribuirlo a nuestro gusto, le hemos añadido `weight=` para que el tráfico de la máquina uno sea el doble que el de la máquina dos. Para combrobar el correcto funcionamiento, usamos `curl http://IP del balanceador`

![Captura 3](http://imgur.com/1esHENc.jpg "Prueba nginx con weight")

En la tarea dos, nos pide configurar una máquina e instalarle el haproxy como balanceador de carga. Por consiguiente, tras instalar haproxy con el comando `sudo apt-get install haproxy` modificamos su configuración básica, situada en `/etc/haproxy/haproxy.cfg`, de tal manera:

![Captura 4](http://imgur.com/fPwMeA9.jpg "Configuración haproxy")

Para combrobar el correcto funcionamiento, usamos `curl http://IP del balanceador` con el que obtenemos el siguiente resultado:

![Captura 5](http://imgur.com/V2FIYFZ.jpg "Prueba haproxy")

Por último, en la tercera tarea, se nos pide someter a la granja web a una alta carga, teniendo primero nginx y después haproxy. Para ello, utilizaremos el comando `ab -n 1000 -c 10 http://192.168.2.121/index.html` y obtenemos los siguientes resultados:

* Para nginx:
	![Captura 6](http://imgur.com/WF7WKpt.jpg "nginx")
* Para haproxy:
	![Captura 7](http://imgur.com/Myj3jNR.jpg "haproxy")