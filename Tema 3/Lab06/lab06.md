Vamos a comenzar con el laboratorio 6:

# Ejercicio 6.1 - Enviando correo usando mail
1. Crear un archivo y enviarlo por correo:
Hemos usado 'echo "Este es un mensaje de prueba." > message.txt' para 
crear el contenido del correo
Luego con 'mail -s "Asunto de prueba" bob@localhost < message.txt' lo 
hemos enviado.

2. Explicar el comando 'echo "Welcome to Network Computer Systems" | mail 
-s "Hello world" bob@anglia.bryant -c smith@anglia.bryant -b 
root@anglia.bryant':
* 'echo "Welcome to Network Computer System" genera el cuerpo del correo.

* 'mail -s "Hello world' define el asunto del correo.

* 'bob@anglia.bryant' es el destinatario principal.

* -c smith@anglia.bryant envía una copia (CC) a Smith.

* -b root@anglia.bryant envía una copia oculta (BCC) a root.

# Ejercicio 6.2 - Revisar correo
1. Inicia sesión con bob:
- Comando: 'su bob'

2. Usar el comando mail para ver los correos recibidos:
- Comando 'mails'
Como vemos aquí nos aparece el mensaje que hemos enviado anteriormente con 
todos los datos establecidos.

# Ejercicio 6.3 - Explorando mail
1. Acciones en 'mail':
* Leer correos: 'mail'

* Responder: 'r [número del mensaje]'

* Enviar nuevo correo: 'mail -s "Asunto" usuario@dominio'

* Eliminar: 'd [número del mensaje]'

* Listar: 'h'

* Guardar: 's [número del mensaje] archivo'

2. Contenido de '/var/spool/mail':
* Contiene los buxones de los usuarios en archivos de texto.

* Implicaciones de seguridad: cualquier usuario con permisos puede leer 
los correos.

3. Enviar correo mediante SMTP usando Telnet:
telnet localhost 25
HELO localhost
MAIL FROM: <tuusuario@localhost>
RCPT TO: <bob@localhost>
DATA
Subject: Prueba Telnet

Este es un mensaje de prueba.
.
QUIT

4. Habilitar POP3:
* Primero editaremos /etc/inetd.conf y descomentaremos la linea POP3.

* Ahora reiniciaremos el servicio:
- Comando 'sudo systemctl restart inetutils-inetd.service'.

5. Interactuar con POP3 mediante Telnet:
telnet localhost 110
USER bob
PASS [contraseña]
LIST
RETR 1
QUIT

6. Puertos utilizados:
* SMTP: 25
* POP3: 110

# Ejercicio 6.4 - Opcional
1. Diferencias entre IMAP y POP3:
* IMAP: Mantiene los correos en el servidor y permite sincronización.
* POP3: Descarga los correos y borra del servidor.

3. PGP Encryption:
* Qué es: un sistema de cifrado para emails.
* Como funciona:
	- Usa claves públicas y privadas.
	- Se cifra con la clave pública del destinatario.
	- Solo el destinatario puede descifrarlo con su clave privada.
* Para usarlo en Debian:
sudo apt install gnupg
gpg --gen--key
gpg --encrypt --recipient bob@localhost mensaje.txt.

Con esto habríamos terminado el laboratorio 6, :)
