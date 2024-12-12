Vamos a comenzar con la actividad de Compose.

1. Lo primero que haremos será preparar el entorno:

- Actualizar los paquetes del sistema:
sudo apt update && sudo apt upgrade -y

- Instalar Docker y Docker Compose:
Docker: sudo apt install docker.io -y
Docker compose: sudo apt install docker-compose -y 
Comprobar versiones: docker/dockerc-compose --version

- Crear un directorio para el proyecto:
mkdir mediawiki-docker && cd mediawiki-docker

2. Configurar docker-compose.yml

- Creamos un archivo docker-compose.yml
Con un nano abrimos el editor y escribimos dentro el contenido, luego 
guardamos.

3. Iniciar los servicios con Docker Compose

- Iniciar los contenedores:
sudo docker-compose up -d

- Verificar que los contenedores estén en ejecución:
sudo docker ps
Podemos ver que está corriendo mediawiki en el puerto 8080

4. Configuración MediaWiki
Para acceder a nuestra página usaremos: http://localhost:8080
