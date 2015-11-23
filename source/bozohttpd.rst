bozohttpd - bozotic httpd 
##########################

::

 httpd - hyper text transfer protocol version 1.1 daemon  (via man httpd)
         httpd(8) lee una peticion por medio del protocolo http y envia la respuesta a la salida standard.

Requerimientos
--------------

NetBSD_ 5 o superior.

Introducción
------------

httpd_ es un servidor web ligero que viene en el sistema base NetBSD y
ejecuta via inetd_, no es necesario instalar paquetes adicionales, tiene
la habilidad de ejecutar scripts cgi,php,c,sh etc. e indexar una lista
de directorios en su caso. El ser ligero lo hace atractivo en sistema
empotrados, en routers, firewall y en sistemas con pocos recursos,
soporta indizado de directorios y virtualhosts ademas de 
ejecutarlo bajo chroot_. Soporta ipv6 tambien.

Usos
----

-  Blog cgi, estatico, php (cgi)
-  Sistemas empotrados.
-  Autenticacion por web.
-  etc.

Configuración
-------------

httpd_\(8) se inicia via inetd_\(8), para ello editamos lo siguiente:

``# vi /etc/inetd.conf``

Descomentar la linea;

``http            stream  tcp     nowait:600      _httpd  /usr/libexec/httpd      httpd /var/www ``

La linea anterior habilita el inicio de httpd_ via inetd, el
directorio /var/www es la ubicacion de nuestros archivos html o cgi,
este directorio ya existe en nuestro sistema, lo que procede es poner
documentos ahi para que httpd_ los lea.

Ahora tambien es posible ejecutar httpd desde el shell, via rc_ de la
siguiente forma:

``# /etc/rc.d/httpd start``

A continuacion ponemos algo dentro del directorio por defecto de httpd :

``# vi /var/www/index.html``

Escribimos una linea html en el archivo y guardamos los cambios,
ejemplo:

::

       <h1> It work's </h1>

A continuacion, iniciamos httpd(8), para ello basta ejecutar desde la
linea de comandos:

``# /etc/rc.d/inetd restart``

Apuntamos nuestro browser hacia **http://localhost** para probar nuestra
configuracion.

Soporte virtualhosts
--------------------
Para usar un servidor httpd_ con soporte para hosts virtuales, es necesario modificar 
la siguiente linea en */etc/inetd.conf*

::

  http stream tcp  nowait:600 _httpd /usr/libexec/httpd httpd -v /var/vroot /var/www

Esta linea indica httpd_ que lea en el directorio /var/vroot en busca de hosts virtuales
Ejemplo:

::
    $ mkdir /var/vroot/netbsd.mx
    $ ln -s /var/vroot/netbsd.mx /var/vroot/netbsd.org.mx
    $ mkdir /var/vroot/docs.netbsd.mx

Ambos netbsd.mx y netbsd.org.mx apuntaran al mismo directorio.

Parametros adicionales
----------------------

::

  -c habilita el uso de scripts cgi, bajo el directorio /var/www/cgi-bin
  -x Permite el indizado de directorios dentro de un directorio particular dentro del DocumentRoot (/var/www en este caso)
  -v Habilita el uso de VirtualHost o servidores virtuales dentro de nuestro DocumentRoot.

Autenticación
-------------

httpd_\(8) soporta autenticación básica a traves de .htpasswd

.. _NetBSD: http://www.netbsd.org
.. _rc: http://netbsd.gw.com/cgi-bin/man-cgi?rc.d++NetBSD-current
.. _httpd: http://netbsd.gw.com/cgi-bin/man-cgi?httpd++NetBSD-current
.. _chroot: http://netbsd.gw.com/cgi-bin/man-cgi?chroot++NetBSD-current
.. _inetd: http://netbsd.gw.com/cgi-bin/man-cgi?inetd++NetBSD-current
