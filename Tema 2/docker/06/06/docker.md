Vamos a comenzar con la actividad 6, gestión de imágenes.

1. Lo primero es descargar la imagen Ubuntu:20.04 desde Docker Hub. Con 
ese comando hemos descargado la imagen.

	- Comando: docker pull ubuntu:20.04

2. Obtener toda la información y volcarla en un fichero info.txt. Podemos 
ver que si entramos en el fichero está toda la información.

	- Comando: docker inspect ubuntu:20.04 > info.txt

3. Ahora tenemos que instanciar la imagen creando un contenedor llamado 
modulo3. Con ese comando hemos instanciado el contenedor.

	- Comando: docker run -d --name modulo3 ubuntu:20.04 tail -f /dev/null

Hemos usado el parámetro 'tail -f /dev/null' porque es una forma común de 
mantener un contenedor activo mientras se pueden realizar operaciones de 
gestión sobre él.

Con docker ps verificamos que efectivamente está en ejecución.

4. Para verificar que el contenedor se ha creado independientemente de que 
esté activo o no usamos el parámetro -a.

	- Comando: docker ps -a

Como resultado podemos ver todos los contenedores, entre ellos modulo3.

5. Intentaremos borrar la imagen.

Nos muestra un error porque hemos creado un contenedor a partir de esa 
imagen y docker no permite eliminar una imagen que está siendo utilizada 
por un contenedor.

	- Comando: docker rmi ubuntu:20.04

6. Para poder borrarla primero tenemos que eliminar el contenedor que está 
usando esa imagen, para ello detenemos el contenedor.

	- Comando: docker stop modulo3

Ahora que hemos detenido el contenedor podemos borrarlo.

	- Comando docker rm modulo3

Y finalmente ya podemos eliminar la imagen porque no hay ningún contenedor 
asociado a ella.

	- Comando: docker rmi ubuntu:20.04

Ahí podemos ver como resultado que se ha borrado la imagen.

Esto es todo.
