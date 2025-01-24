Vamos a comenzar con el laboratorio 4:

# Ejercicio 4.1: Explorar procesos en ejecución:
1. Listar todos los procesos, eso lo hacemos con el siguiente comando:
- ps aux, así que vemos todos los procesos de la máquina.

2. Identificar los procesos más intensivos en CPU:
Esto lo conseguimos con el comando "top".
Para salir pulsamos la tecla 'q'. 
Podemos ver los procesos dinamicamente.

3. Filtrar los procesos relevantes:
Usaremos el comando 'ps aux --sort=-%cpu | head -n 10'
Esto muestra los 10 procesos más intensivos.

4. Investiga los procesos:
Esto podemos hacerlo usando el comando 'man' junto con el nombre de cada 
proceso y nos llevará a una página man mostrandonos la información de 
dicho proceso.

# Ejercicio 4.2: Explorando procesos de red:
1. Ejecutar 'nmap localhost':
Primero debemos instalar nmap. Ya lo tenmos.
Este comando lista los puertos abiertos en la máquina y los servicios 
asociados.

2. Buscar procesos específicos:
Con el comando 'ps aux | grep sshd' mostramos procesos relacionados con 
SSH.

3. Iniciar un servicio:
Con el comando 'sudo systemctl start ssh' iniciamos un servicio.
Con el comando 'systemctl status ssh' comprobamos que está en ejecución.

4. Detener un proceso:
Con el comando ps aux | grep sshd encontramos el PID del proceso.
El PID sería 405.
Lo paramos con  'sudo kill -9 405'.
Verificar que se ha detenido. Con el comando 'ps aux | grep sshd'.

# Ejercicio 4.3: Explorando las señales de UNIX:
1. Ejecutar el comando 'kill -l'

2. Como vemos aparece una lista con las señales de interés.
Por ejemplo: 
- (SIGUSR1): Señal personalizada para el usuario.
- (SIGSEGV): Violación de segmentación (segfault).
- (SIGUSR2): Señal personalizada para el usuario 2.
- (SIGPIPE): Intento de escribir en un pipe roto.
- (SIGALRM): Alarma por temporizador.

# Ejercicio 4.4: Procesos y redes:
1. Verificar que la cuenta de usuario bob existe:
Comando: cat /etc/passwd | grep bob

2. Habilitar FTP y Telnet:

# Ejercicio 4.5: Opcional:
1. Combinar pidof con kill -HUP para reiniciar inetd:

2. FTP como root: 

Ya estaría terminada la actividad, un saludo  :)
