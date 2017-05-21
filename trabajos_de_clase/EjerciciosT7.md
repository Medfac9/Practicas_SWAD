# Tema 7

### Ejercicio 1
¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de dos discos de 100 GB y 100 GB?

El tamaño de unidad del RAID sería de 200GB ya que se reparte la información entre todo el espacio disponible.

¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de tres discos de 200 GB cada uno?

Al igual que el anterior, el espacio se reparte, por lo que, 200GB * 3 = 600GB.

### Ejercicio 2
¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de dos discos de 100 GB y 100 GB?

El tamaño de unidad del RAID sería de 100GB pues se replica la información en ambos discos.

¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de tres discos de 200 GB cada uno?

El tamaño de unidad del RAID sería de 200GB pues se replica la información en cada uno de los discos.

### Ejercicio 3
Buscar información sobre los sistemas de ficheros en red más utilizados en la actualidad y comparar sus características. Hacer una lista de ventajas e inconvenientes de todos ellos, así como grandes sistemas en los que se utilicen.

Los sistemas de ficheros en red más utilizados son NFS y Server Message Block.
NFS está dividido en dos partes, servidor y clientes. Los clientes acceden de manera remota a los datos almacenados en el servidor. De esta manera las estaciones de trabajo locales utilizan menos espacio de disco.
Server Message Block (SMB) es un protocolo de red que permite compartir archivos e impresoras entre nodos de una red usado principalmente en ordenadores con Windows y DOS. 