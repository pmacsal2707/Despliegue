Vamos a comenzar con la actividad 7, volúmenes.

1. Lo primero que vamos a hacer es crear dos volúmenes con el comando 
docker volume.

	- Comando: docker volume create volumen_datos
	- Comando: docker volume create volumen_web

Con estos dos comandos hemos creado dos volúmenes.

2. Ahora arrancaremos los contenedores que se piden.

* Contenedor c1 - imagen php:7.4-apache

	- Comando: docker run -d --name c1 -v volumen_web:/var/www/html 
	php:7.4-apache

Con esto hemos creado el primer contenedor a partir de la imagen de php.

* Contenedor c2 - imagen mariadb

	- Comando: docker run -d --name c2 -v volumen_datos:/var/lib/mysql -e 
	MYSQL_ROOT_PASSWORD=admin mariadb

Con esto hemos creado el segundo contenedor con la imagen de mariadb y 
cuya contraseña root sea admin.

3. Ahora vamos a parar y borrar el contenedor c2 y luego borraremos el 
volumen volumen_datos.

* Contenedor:

- Primero lo paramos.

	- Comando: docker stop c2

- Ahora lo borramos.

	- Comando docker rm c2

* Volumen, lo borramos:

	- Comando: docker volume rm volumen_datos

Con esto habríamos parado y borrado el contenedor c2 y luego hemos borrado 
el volumen volumen_datos.

Esto es todo.
