# Práctica 6

En la primera parte de la práctica 6 se pide configurar dos discos en RAID 1. Para ellos, hemos añadido dos discos, con el mismo tamaño, a nuestro servidor 1 como se puede apreciar en la foto:

![Captura 1](http://imgur.com/C2jbRfK.jpg "Discos creados")

Seguidamente, buscamos la identificación de ambos discos con el comando `sudo fdisk -l` y vemos que nuestros discos son sdb y sdc:

![Captura 2](http://imgur.com/ybx8Ojx.jpg "Discos")

A continuación, creamos el RAID 1 con el siguiente comando `sudo mdadm -C /dev/md0 --level=raid1 --raid-devices=2 /dev/sdb /dev/sdc`, le damos formato con `sudo mkfs /dev/md0`, y creamos el directorio donde se montará el RAID `sudo mkdir /dat` y `sudo mount /dev/md0 /dat`:

![Captura 3](http://imgur.com/cAyZO1y.jpg "RAID")
![Captura 4](http://imgur.com/MQX2xUD.jpg "Formato")

Para mirar comprobar el estado del RAID ejecutamos el comando `sudo mdadm --detail /dev/md0`:

![Captura 5](http://imgur.com/ufysyLm.jpg "Estado RAID")

Si todo está correcto, debemos obtener los datos UUID de nuestro RAID y anotarlos. Para ello usaremos `ls -l /dev/disk/by-uuid/`:

![Captura 6](http://imgur.com/Pq6rFy9.jpg "UUID")

Después, debemos añadir estos datos al final del archivo `/etc/fstab`:

![Captura 7](http://imgur.com/zk6FB01.jpg "Añadir UUID")

Ya tenemos todo funcionando correctamente. Procedemos a realizar la segunda parte de la práctica, que consiste en simular el fallo de un disco y cambiarlo "en caliente".
Para ellos primero simulamos el fallo de uno de los dos discos y comprobamos su estado:

![Captura 8](http://imgur.com/IMioTQA.jpg "Falla disco")

A continuación, borramos el disco que falla y volvemos a comprobar el estado:

![Captura 9](http://imgur.com/gpWMYIY.jpg "Eliminamos disco")

Por último, añadimos el disco "en caliente" y comprobamos su estado. Como se puede observar, tarda un poco en cargar el disco y por eso comprobamos su estado dos veces:

![Captura 10](http://imgur.com/wVvItlA.jpg "Añadiendo disco")
![Captura 11](http://imgur.com/Um5sLpI.jpg "Añadido disco")