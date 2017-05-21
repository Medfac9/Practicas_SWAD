# Tema 4

### Ejercicio 1
Buscar información sobre cuánto costaría en la actualidad un mainframe. Comparar precio y potencia entre esa máquina y una granja web de unas prestaciones similares.

No se conoce el precio del mainframe z13 (de IBM), pero se estima que supere los 80.000$. El costo, sería mucho más alto que el de una granja web de unas prestaciones parecidas.

### Ejercicio 2
Buscar información sobre precio y características de balanceadores hardware específicos. Compara las prestaciones que ofrecen unos y otros.

| Modelos                           | KEMP LM-5400 | F5 Networks LTM-2000s | Citrix MPX-8005 |
| --------------------------------- | ------------ | --------------------- | --------------- |
| Precio                            | 17990$       | 17995$                | 25000$          |
| Max Throughput (GBs)              | 10.02        | 5                     | 5               |
| Número de fuentes de alimentación | 2            | 1                     | 1               |
| Consumo (W)                       | 184.5        | 74                    | 185             |

### Ejercicio 3
Buscar información sobre los métodos de balanceo que implementan los dispositivos recogidos en el ejercicio 4.2

Todos los anteriores implementan Round-Robin

### Ejercicio 4
Instala y configura en una máquina virtual el balanceador ZenLoadBalancer.

Primeramente, debemos de descargar la ISO de su página oficial. Una vez descargada vamos siguiendo los pasos que nos van saliendo como añadir la localización, idioma, etc. Una vez instalado ya habremos acabado y tendremos el balanceador listo para usarlo. 

### Ejercicio 5
Probar las diferentes maneras de redirección HTTP. ¿Cuál es adecuada y cuál no lo es para hacer balanceo de carga global? ¿Por qué?

Las maneras adeacuadas de redirección HTTP son la 301, 302, 303, 307 y 308.

### Ejercicio 6
Buscar información sobre los bloques de IP para los distintos países o continentes. Implementar en JavaScript o PHP la detección de la zona desde donde se conecta un usuario.

Para detectar la zona desde donde se conecta un usuario primeramente debemos localizar su IP. Una vez sabida su IP, utilizaremos una API  la cual nos devuelve la localización del usuario.

### Ejercicio 7
Buscar información sobre métodos y herramientas para implementar GSLB.

Primero debemos de tener dos localizaciones que queremos comunicar, deberían estar a bastante distancia ya que no tiene sentido montar GSLB en un mismo país. A continuación, configuramos el balanceador para que detecte la localización y mande al usuario al servidor más cercano.