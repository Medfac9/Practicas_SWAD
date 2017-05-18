# Práctica 5

Primeramente, para crear una base de datos, entramos a mysql en modo root con el comando `mysql -uroot -p` y a continuación usamos `create database contactos;`, `use contactos;`, `create table datos(nombre varchar(100),tlf int);` y con `show tables;` podemos ver la tabla creada.
![Captura 1](http://imgur.com/86mnOw1.jpg "Tabla creada")

Pdemos introducir los datos con `insert into datos(nombre,tlf) values ("pepe",95834987);` y `select * from datos;` para ver la tabla.
![Captura 2](http://imgur.com/Zf5uTPY.jpg "Tabla rellenada")

A continuación, vamos a realizar una copia de seguridad de nuesetra base de datos de la máquina uno. Accedemos a mysql en modo root, y seguidamente usamos el comando `FLUSH TABLES WITH READ LOCK;`, salimos de mysql y seguidamente realizamos la copia con `mysqldump contactos -u root -p > /tmp/contactos.sql` y como habiamos bloqueado la tabla a continuación accedemos a mysql y la desbloqueamos `UNLOCK TABLES;`.
![Captura 3](http://imgur.com/cnLCqd3.jpg "Tabla copiada")

Ahora nos vamos a la máquina dos para copiar la copia de seguirdad de la base de datos de la máquina uno. Para ello, en la máquina dos usamos el comando `scp rafa@192.168.56.101:/tmp/contactos.sql /tmp/`.
![Captura 4](http://imgur.com/vXMC3jU.jpg "Tabla pasada")

Una vez tenemos el archivo en la máquina dos, procedemos a importar la base de datos. Para ello creamos la tabla con `CREATE DATABASE contactos;` y seguidamente restauramos los datos.
![Captura 5](http://imgur.com/elg6LCe.jpg "Tabla importada")
![Captura 6](http://imgur.com/rdSxP5x.jpg "Bien copiada")

Ahora vamos a realizar la configuración maestro-esclavo de los servidores MySQL para que la replicación de datos se realice automáticamente. Primeramente, en la máquina maestro debemos de acceder a la siguiente ruta: `/etc/mysql/mysql.conf.d/mysqld.cnf` y comentamos la línea de `#bind-address 127.0.0.1` y descomentamos la linea `server-id = 1`. Seguidamente, en la máquina esclava comentamos y descomentamos ambas líneas, con la diferencia que ponemos `server-id = 2`.
![Captura 7](http://imgur.com/3DD1NGv.jpg "Comentar")
![Captura 8](http://imgur.com/zSS6pkR.jpg "Descomentar 1") 
![Captura 9](http://imgur.com/U88Gf3W.jpg "Descomentar 2")

Guardamos el documento y reiniciamos el servicio: `/etc/init.d/mysql restart`.
A continuación, nos vamos a la máquina esclava y la configuramos como en la siguiente captura de pantalla:
![Captura 10](http://imgur.com/dUWGLAi.jpg "Creamos el esclavo")
![Captura 11](http://imgur.com/rFRxKlz.jpg "Creamos el esclavo")

Seguidamente, nos vamos a la máquina maestra y la configuramos como en la siguiente captura de pantalla:
![Captura 12](http://imgur.com/v833Pu5.jpg "Creamos el maestro")

Por último, vamos a la máquina maestro y desbloqueamos las tablas con `UNLOCK TABLES;` y para asegurarnos que todo está correcto, en la máquina esclava, usamos el siguiente comando: `SHOW SLAVE STATUS\G` y si Seconds_Behind_Master es 0 está todo correcto.
![Captura 13](http://imgur.com/1ZyNOBK.jpg "Todo correcto")

Hacemos la prueba de introducir un nuevo dato en la máquina uno y vemos que en la máquina dos se copia automáticamente.
![Captura 14](http://imgur.com/EZGQE3R.jpg "Máquina 1")
![Captura 15](http://imgur.com/Dfv6D0s.jpg "Máquina 2")