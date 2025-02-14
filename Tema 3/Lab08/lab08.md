Vamos a comenzar con el laboratorio 08, MySQL:

# Ejercicio 8.1: 
1. Encontrar el número de entradas en la tabla 'user' de la base de datos mysql:
- Comando: SELECT User, Host FROM mysql.user;
Aqui podemos ver una lista de usuarios y sus hosts asociados.

2. Comandos para crear y eliminar una tabla, seleccionar datos e insertar 
datos en una tabla:
* Crear una tabla:
- Comando:
CREATE TABLE tabla1 (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    edad INT
);

Primero crearemos una base de datos
- Comando: 'CREATE DATABASE prueba;'

* Eliminar una tabla:
- Comando: 'DROP TABLE tabla1;'

* Seleccionar datos de una tabla:
- Comando: 'SELECT * FROM tabla1;'
Este comando no muestra nada porque la tabla está vacía, para ello vamos a 
agregar datos en la tabla:

* Insertar datos en una tabla:
- Comando: 'INSERT INTO tabla1 (nombre, edad) VALUES ('Juan', 25);'
Ahora si volvemos a mostrar los datos de la tabla nos debe salir el nuevo 
registro:
Efectivamente nos sale Juan, de 25 años con un id que se asigna 
automaticamente de manera creciente, es decir, el siguiente será de id 2. 
Esto lo conseguimos gracias al parámetro 'AUTO_INCREMENT'.

3. Crear la base de datos 'nselab' y la tabla 'users':
Comandos:
- CREATE DATABASE nselab;
- USE nselab;
- CREATE TABLE users (
    studentid INT AUTO_INCREMENT PRIMARY KEY,
    firstname VARCHAR(25) NOT NULL,
    lastname VARCHAR(25) NOT NULL
);
- INSERT INTO users (firstname, lastname) VALUES ('Joe', 'Bloggs'), 
('Ashley', 'Smith');
- SELECT * FROM users;

Gracias a estos comandos hemos creado la base de datos, hemos entrado en 
ella, hemos creado una tabla y luego hemos insertado 2 registros.

* Insertar un registro sin studentid funciona gracias al parámetro 
'AUTO_INCREMENT'.
* Insertar un campo 'null', 'firstname' o 'lastname', fallaría porque 
hemos usado el parámetro 'not null' que impide que introduzcamos un 
parámetro 'null'.
* Insertar nombres de más de 25 caracteres también falla porque hemos 
usado 'varchar(25)' que impide que superemos ese número de caracteres.

# Ejercicio 8.2 (Opcional):
1. Crear el usuario 'adminsec' y asignarle permisos solo en nslab:
Comandos:
- CREATE USER 'adminsec'@'localhost' IDENTIFIED BY 'password123';
- GRANT ALL PRIVILEGES ON nselab.* TO 'adminsec'@'localhost';
- FLUSH PRIVILEGES;

2. Crear una página PHP para mostrar los datos de la tabla users:
Para ello vamos a crear un archivo PHP, yo voy a pegarlo porque lo creé en 
VSCode:

Este sería el archivo, esto generará una tabla en HTML mostrando los datos 
almacenados en 'users'.

Esto sería todo, un saludo :)
