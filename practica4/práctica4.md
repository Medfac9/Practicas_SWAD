# Práctica 4

Para instalar un certificado SSL autofirmado para configurar el acceso HTTPS a los servidores, deberemos irnos a nuestra máquina uno y poner el comando `a2enmod ssl` después crearemos la carpeta donde guardaremos nuestro certificado `mkdir /etc/apache2/ssl` y ejecutamos el siguiente comando:

![Captura 1](http://imgur.com/3A4UhW6.jpg "Instalar certificado SSL")

Tras editar el archivo de configuración de ssl y agregando las siguientes lineas: `SSLCertificateFile /etc/apache2/ssl/apache.crt` y `SSLCertificateKeyFile /etc/apache2/ssl/apache.key`. Reiniciamos apache y probamos en nuestro navegador que al accedes al servidor we mediante HTTPS sale en rojo el https ya que se trata de un certificado autofirmado.

A continuación, para configurar las reglas del cortafuegos con IPTABLES, nos iremos a la carpeta `/etc/init.d` e crearemos nuestro script.

![Captura 2](http://imgur.com/N95Wt9k.jpg "Script IPTABLES")

Tras guardar el script, ejecutaremos la orden `update-rc.d miScript.sh defaults` para que se ejecute el script cada vez que se inicie la máquina.