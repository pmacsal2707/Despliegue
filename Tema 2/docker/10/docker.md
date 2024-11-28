Vamos a comenzar con la actividad 10, dockerfile.

## 1a Parte:

1. Arrancar contenedor de ubuntu:

	Comando: docker run -it --name ubuntu_mod ubuntu:20.04

2. Instalar nano:

	Comando: apt install -y nano

3. Instalar vim:

	Comando: apt install -y vim

4. Instalar herramientas de red:

	Comando: apt install -y inetutils-tools

5. Instalar herramientas DNS:

	Comando: apt install -y dnsutils

6. Crear un usuario 'usuario' con contraseña usuario

	Comando: adduser usuario


-- Ahora guardaremos los cambios del contenedor como una imagen nueva:

	Comando: docker commit ubuntu_mod pmacsal470/a61

-- Ahora subiremos la imagen a Docker Hub:

	Comando: docker login - con esto iniciaremos sesión. Yo ya había 
	iniciado sesión anteriormente.

	Comando: docker push pmacsal470/a61 - con esto hemos subido la 
	imagen a la nube.

Si accedemos a nuestra cuenta de Docker Hub veremos el nuevo repositorio 
junto con la imagen que acabamos de subir.

## 2a Parte

1. Crear en nuestra máquina un directorio para el proyecto y entrar en él:

	Comando: mkdir docker_php && cd docker_php

2. Crear un archivo llamado Dockerfile:

	Comando: nano Dockerfile

3. Escribir el contenido de Dockerfile:

Con este fichero conseguimos varias cosas:
- Crear una imagen personalizada basada en php:7.4-apache que instale nano 
y git.
- Copiando index.html e info.php al directorio raíz de Apache preparamos 
el contenedor para servir estas imágenes directamente al arrancar.
- Y finalmente automatizamos el proceso ya que esto se ejecuta 
automaticamente.

4. Crear los archivos requeridos en el mismo directorio:

	Comando: nano index.html

	Comando: nano info.php

-- Finalmente vamos a construir la imagen Docker:

	Comando: docker build -t pmacsal470/a62 . - Con este comando hemos 
	construido la imagen

	Comando: docker push pmacsal470/a62 - Con este comando hemos 
	subido la imagen a docker hub

## Esto es toda la actividad, ADIOS ##
