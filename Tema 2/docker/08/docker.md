Vamos a comenzar con la actividad 8, bind mounts.

1. Lo primero que haremos será crear la carpeta saludo y dentro el archivo 
index.html.

	- Comando: mkadir para crear la carpeta
	- Comando: nano para crear el archivo html dentro de la carpeta

2. Ahora vamos a crear dos contenedores basados en la imagen 
php:7.4-apache.

* Contenedor c1:

Me da conflicto porque en la actividad anterior creé un contenedor con ese 
mismo nombre, así que lo borraré y volveré a usar el mismo comando.

Ahora podemos volver a usar el comando.

	- Comando: docker run -d --name c1 -p 8181:80 -v ~/saludo:/var/www/html 
	php:7.4-apache

Ahora sí ha funcionado, con esto hemos creado un contenedor con nombre c1, 
mapeando el puerto 80 del contenedor al puerto 8181 de mi máquina física. 
Y además hemos hecho el bind mount de la carpeta /saludo en el directorio 
/var/www/html.

* Contenedor c2:

	- Comando: docker run -d --name c2 -p 8282:80 -v ~/saludo:/var/www/html 
	php:7.4-apache

Con esto hemos creado el segundo contenedor llamado c2 mapeando el puerto 
80 del propio contenedor al puerto 8282 de mi máquina física.

Esto es todo
