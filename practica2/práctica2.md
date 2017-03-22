# Práctica 2
Para el primer ejercicio hay que comprobar el correcto funcionamiento de la copia de archivos por ssh, para ello usamos el comando `scp prueba.html rafa@192.168.56.101:/var/www` esta orden copiaría el archivo desde la máquina en la que se ejecuta la orden, hasta la que se realiza el ssh. En la siguiente foto se aprecia como al usar el comando el archivo prueba.html se pasa de la máquina dos a la uno.

![Captura 1](http://imgur.com/AfHnfxf.jpg "Captura de la prueba")
![Captura 2](http://imgur.com/fDOh3r7.jpg "Captura de la prueba")

Para el ejercicio dos hay que clonar una carpeta entre las dos máquina. En las capturas siguientes se muestra como se copia en la máquina dos la carpeta /var/www/ de nuestra máquina uno con la siguiente orden `rsync -avz -e ssh 192.168.56.109:/var/www/ /var/www/`

![Captura 3](http://imgur.com/cz0MPUa.jpg "Captura de la prueba")
![Captura 4](http://imgur.com/xV4Ook1.jpg "Captura de la prueba")

Para el ejercicio tres debemos de configurar ssh para acceder sin que solicite contraseña. Para ello, usamos el comando `ssh-keygen -b 4096 -t rsa` para generar una key en nuestra máquina dos y la copiamos con la siguiente instrucción `ssh-copy-id 192.168.56.109` en la maquina uno. En la siguiente captura se muestra como hemos conseguido acceder por ssh a la máquina uno sin que nos solicite contraseña.

![Captura 5](http://imgur.com/xysUvyK.jpg "Captura de la prueba con ssh")

Para el último ejercicio, en el que tenemos que establecer una tarea en cron que se ejecute cada hora para mantener actualizado el contenido del directorio /var/www entre las dos máquinas. Para ello, usamos el comando `sudo nano /etc/crontab` con el que se nos abrira el editor de texto para editar el contenido del cron. Lo único que tendremos que hacer es poner una linea en la que se muestre la tarea que se quiere realizar y la frecuencia con la que se realiza. En la siguiente imagen se aprecia como cada hora se copia la carpeta /var/www/ de la máquina uno en la máquina dos todos los días y todos los meses.

![Captura 6](http://imgur.com/6YbTbFM.jpg "Captura de la prueba con ssh")