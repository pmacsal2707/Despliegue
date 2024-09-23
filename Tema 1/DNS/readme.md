# DNS
## Resolución:
La resolución DNS es el proceso por el cual se traduce un nombre de dominio en su dirección IP correspondiente. Este proceso generalmente implica:

El cliente realiza una consulta DNS al servidor DNS local o recursivo.
Si el servidor recursivo no tiene la respuesta en caché, realiza consultas iterativas a otros servidores DNS hasta encontrar la respuesta.
Finalmente, el servidor autoritativo proporciona la respuesta al servidor recursivo, que luego la envía al cliente.

## Nombre de Dominio:
 Un nombre de dominio es un identificador único y legible por humanos que representa un dominio en el sistema de nombres de dominio (DNS)
 Por ejemplo, en "www.example.com":
 
 "example" es el dominio principal
 ".com" es el dominio superior (TLD - Top Level Domain)
 "www" es el subdominio

## Nivel de Dominio:
 El sistema de nombres de dominio tiene una estructura jerárquica con varios niveles:
 
 Nivel superior (.com, .org, etc.)
 Nombre de dominio (por ejemplo, ejemplo.com)
 Subdominios (por ejemplo, soporte.ejemplo.com)
 Subsubdominios (por ejemplo, foro.soporte.ejemplo.com)

## Zonas de Búsqueda:
 El DNS utiliza zonas para organizar la información. Cada zona corresponde a un dominio específico y contiene información relevante para ese dominio.

## Tipos de Servidores:
 ### Los principales tipos de servidores DNS son:
  Existen varios tipos de servidores DNS involucrados en el proceso de resolución:
  
  Servidor Raíz: Contiene información sobre todos los servidores TLD.
  Servidor TLD (Top Level Domain): Maneja dominios superiores como .com, .org, etc.
  Servidor Autoritativo: Contiene información específica para un dominio particular.
  Servidor Recursivo: El primero en contactar con el cliente y realizar consultas si necesario.

## Registros:
 Los registros DNS son entradas en el sistema DNS que contienen información relacionada con un dominio específico. Son como una base de datos que relaciona nombres legibles por humanos con direcciones IP y otros datos técnicos.

## Funcionamiento:
El funcionamiento básico de DNS implica dos tipos principales de consultas:

Consulta Recursiva: El cliente realiza una consulta completa al servidor recursivo, que puede necesitar consultar con otros servidores si es necesario.
Consulta Iterativa: El servidor recursivo devuelve la mejor respuesta posible y proporciona referencias a servidores potencialmente capaces de resolver el nombre.
Este proceso permite que los usuarios accedan a recursos en internet utilizando nombres memorables en lugar de direcciones IP numéricas.
