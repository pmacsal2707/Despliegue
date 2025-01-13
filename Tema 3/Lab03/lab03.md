Vamos a comenzar con el laboratorio 3:

-- Ejercicio 3.1:
1. Abrimos y editamos el archivo con vi:
Lo que hemos hecho ha sido crear el archivo y una vez dentro hemos pulsado 
la tecla 'i' para entrar en modo edición, luego lo hemos editado y cuando 
hemos terminado hemos pulsado 'esc' y hemos escrito ':wq' para salir 
guardando.

2. Hacer el script ejecutable y ejecutarlo:
Con esto lo que hemos hecho es conceder el privilegio de ejecución del 
archivo al propietario del archivo a través del comando 'chmod +x 
test.sh'.
Luego lo hemos ejecutado escribiendo './test.sh'.

Por qué chmod 777 es una mala idea:
En los sistemas linux, otorgar permisos 777 con 'chmod 777 test.sh' es 
mala práctica porque cualquier usuario del sistema podría modificarlo o 
ejecutar el script, lo que incluye a usuarios maliciosos. Ademas 
compromete la seguridad porque si el script contiene comandos delicados, 
podría ser usado para dañar el sistema.

Una alternativa sería usar permisos 755 para restringir los permisos de 
escritura a otros.

-- Ejercicio 3.2:
1. Crear usuarios bob y smith:
Hemos usado el comando adduser para crear los 2 usuarios y luego hemos 
hecho un cat junto con un grep para buscar el el fichero /etc/passwd si 
existen y efectivamente se han creado.

-- Ejercicio 3.3:
1. Crear directorio público con permisos adecuados:
Hemos creado el directorio /home/ncs con todos los permisos para todos los 
usuarios.

2. Crear script hello.sh usando vi:
Hemos creado el archivo, lo hemos editado y luego hemos guardado.

3. Hacer el script ejecutable:

4. Ejecutar el script:
Como podemos ver el resultado es el esperado, se muestra hello world

5. Verificar los permisos y propietarios del script:
Finalmente vemos como el script tiene permiso de ejecución para todos los 
usuarios.

-- Ejercicio 3.4:
#Como usuario bob:
1. Iniciar sesión como bob:
Con el comando su - bob

2. Navegamos hacia /home/ncs con cd y con ls comprobamos que el script 
esté.
En este directorio podemos ver el sript hello.sh

3. Ejecutamos el script con ./hello.sh
Como vemos el script funciona porque tenemos permisos de ejecución.

4. Crear un script propio bob.sh
Como vemos, al crear el archivo y ejecutarlo se muestra correctamente. Ya 
que tenemos permisos de ejecución.

#Como usuario smith:
1. Iniciar sesión:
Con el comando su - smith

2. Navegar al directorio /home/ncs. Aquí vemos hello.sh y bob.sh

3. Ejecutar ambos scripts:
Como podemos ver ambos scripts muestran correctamente el mensaje porque 
todos los usuarios tienen privilegios para ejecutarlos, sin embargo 
podemos cambiarlo, vamos a poner en el script bob.sh que solo lo podemos 
ejecutar desde el usuario bob, y probaremos a ejecutarlo desde smith.

Con el comando 'chmod 700 bob.sh' solo bob tiene permisos sobre 'bob.sh', 
así que vamos a ejecutarlo desde smith.

Como resultado nos dice que no tenemos permiso y es correcto porque este 
archivo solo lo puede ejecutar bob, de esta forma podemos controlar los 
permisos.

-- Ejecicio 3.5:
1. Crear el grupo sysadmins y añadir a los usuarios:
- Crear el grupo - groupadd sysadmins
- Añadir los usuarios - sudo usermod -aG sysadmins (user)
Con el comando groups vemos como ambos usuarios han sido añadidos 
correctamente.

2. Cambiar el grupo propietario y permisos del directorio y los scripts:
- sudo chown  :sysadmins /home/ncs/ - con esto cambiamos el propietario 
del directorio o archivo
- sudo chmod 770 /home/ncs/bob.sh - con esto cambiamos los privilegios del 
archivo

Ahora solo los usuarios que estén en el grupo sysadmins podrán ejecutar 
los scripts.

# Deshabilitar el usuario smith:
- sudo usermod --expiredate 1 smith - esto desactiva la cuenta sin 
eliminar sus archivos.

Si intentamos entrar no nos deja porque está actualmente desactivada, así 
que ha funcionado.

Finalmente hemos terminado la actividad, un saludo :)
