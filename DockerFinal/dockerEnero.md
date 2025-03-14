Vamos a comenzar con la actividad de subida de nota de docker:

# 1. Descargar imágenes necesarias:
php:7.4-apache y mariadb:latest
- Comando: docker pull php:7.4-apache
  ![](images/apache.png)
- Comando: docker pull mariadb:latest
  ![](images/mariadb.png)  

Con el comando 'docker images' podemos ver todas las imagenes que tenemos 
instaladas.
Ahí vemos que ya tenemos lo necesario.

# 2. Ejercicio 1: Desplegar un Servidor WordPress en el Puerto 8181:
1. Crear la estructura de carpetas:
- Comando: mkdir -p ~/Music/docker1/wp
- Comando: mkdir -p ~/Music/docker1/data
  ![](images/Screenshot_20250312_132351.png)

2. Crear el archivo docker-compose.yml en ~/Music/docker1:
Aquí podemos ver el contenido del archivo.
![](images/Screenshot_20250312_140439.png)

4. Iniciar los contenedores:
- Comando: cd ~/Music/docker1
- Comando: docker-compose up -d
  ![](images/Screenshot_20250312_140639.png)

4. Verificar que los contenedores están corriendo:
- Comando: docker ps
  ![](images/Screenshot_20250312_184418.png)
Como vemos ya tenemos los dos contenedores listos.

# Ejercicio 2: Replicar el Servidor en otros puertos:
1. Crear dos nuevas carpetas:
- Comando: mkdir -p ~/Music/docker2/wp ~/Music/docker2/data
- Comando: mkdir -p ~/Music/docker3/wp ~/Music/docker3/data
  ![](images/Screenshot_20250312_184444.png)

2. Hemos copiado el archivo docker-compose.yml que había en docker1 y 
hemos cambiado el puerto 8181 por 8282 y 8383.

3. Lanzamos los nuevos servicios:
- Comando: docker-compose up -d
  ![](images/Screenshot_20250312_194146.png)
  ![](images/Screenshot_20250312_194109.png)

4. Verificamos que los contenedores están corriendo:
- Comando: docker ps
  ![](images/Screenshot_20250312_194701.png)
Como vemos están ya todos los contenedores corriendo.

Esto es todo, hasta la próxima :)
