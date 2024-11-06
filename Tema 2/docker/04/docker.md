Vamos a comenzar la actividad.

1. Primero vamos a crear y arrancar el contenedor con la imagen 
especificada de php. Con este comando podemos ejecutar el contenedor en 
segundo plano, gracias al parámetro -d, además le hemos asignado el nombre 
y el puerto que pedia el enunciado.

Luego hemos verificado que esté corriendo con el comando docker ps.

2. Ahora que el contenedor está en ejecución vamos a colocar los archivos 
index.html e index.php en el directorio raíz de dicho contenedor.

Para ello lo primero que vamos a hacer será crear los archivos y luego 
copiarlos al directorio raíz.

Ahora los archivos index.html e index.php están en el directorio 
/var/www/html dentro del contenedor web.

3. Vamos a crear un contenedor con la imagen mariadb.

Antes de arrancar el contenedor visitaremos la página de docker para 
establecer las variables de entorno necesarias. Usaremos:
- MYSQL_ROOT_PASSWORD para establecer la contraseña de root
- MYSQL_DATABASE para crear la base de datos automaticamente
- MYSQL_USER y MYSQL_PASSWORD para crear un usuario con contraseña

Finalmente hemos visto como el contenedor estaba activo, ahora voy a 
mostrarlo de nuevo:

Aquí podemos ver como ambos contenedores están en ejecución, voy a pegar 
aquí el comando que usé para el último contenedor porque en consola no se 
ve muy bien:
docker run -d --name bbdd -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=prueba 
-e MYSQL_USER=invitado -e MYSQL_PASSWORD=invitado -p 3336:3306 mariadb

Esto sería todo
