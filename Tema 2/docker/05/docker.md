En esta tarea vamos a obtener la información de los contedores.

1. Obtener dirección IP del contenedor web. - Vemos que la ip es 
172.17.0.2

Comando: docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web

2. Redirección de puertos del contenedor web.
Aquí podemos ver como el puerto 80 dentro del contenedor está mapeado al 
puerto 8181 de mi máquina local.

Comando: docker port web

3. Dirección IP del contenedor bbdd. - Vemos que la ip de este contenedor 
es la 172.17.0.3

Comando: docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' bbdd

4. Redirección de puertos del contenedor bbdd.
Aquí podemos obsevar que el puerto 3306 dentro del contenedor bbdd está 
mapeado al puerto 3336 de mi máquina local. - 0.0.0.0 indica que el puerto 
3336 está accesible desde todas las interfaces de red de mi máquina.

Esto es todo.
