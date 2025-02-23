Vamos a comenzar con el laboratorio 7:

1. Instalación de Apache y PHP:

2. Configuración de Apache:

# Ejercicio 7.1: Configurar Apache:
Reiniciamos apache.

3. Iniciar, detener y verificar el estado de Apache:
Como podemos ver, hemos iniciado, parado y reiniciado Apache y luego vemos 
que efectivamente está corriendo.

# Ejercicio 7.2:
* 'ps aux' muestra los procesos en ejecución.
* 'grep apache2' filtra los procesos relacionados con Apache.
* '|' se usa para conectar comandos y filtrar la salida.

4. Crear y visualizar archivos HTML.
Hemos creado un html en '/var/www/html/test.html' y hemos agregado 
contenido.

Para ver el resultado debemos acceder a 'http://127.0.0.1/test.html' con 
el navegador.

# Ejercicio 7.3:
Para ver los permisos del archivo usamos el comando 'ls -l 
/var/www/html/test.html'.
Podemos ver que tiene permisos '-rw-r--r--', lo que significa que el 
propietario 'root' puede leer y escribir, mientras que el grupo 'root' y 
otros usuarios sólo pueden leer.

5. Crear y visualizar archivos PHP:
Hemos creado un PHP y le hemos añadido contenido. Para verlo debemos 
acceder a 'http://127.0.0.1/nse.php'.

6. Modificar el archivo hosts:
Con esto asignamos un dominio local a la dirección IP 127.0.0.1. De esta 
forma al entrar en www.ejemplo.com estaremos accediendo a nuestro propio 
servidor local.

7. Autenticación con .htpasswd:
Ahora tenemos que añadir esto a 'Directory /var/www/html':
AuthType Basic
AuthName "Autorización requerida"
AuthUserFile /etc/apache2/.htpasswd
Require valid-user

Reiniciamos apache:

Ahora ya podemos acceder a http://127.0.0.1 y nos pedirá el usuario y la 
contraseña que hemos asignado a través de
'sudo htpasswd -c /etc/apache2/.htpasswd usuario'.

Ya hemos terminado, hasta la próxima :)

