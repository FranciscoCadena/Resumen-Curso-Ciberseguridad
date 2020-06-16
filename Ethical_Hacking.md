# Ethical Hacking

Este curso prácticamente es como una introducción a los demás cursos de seguridad, porque se habla un poco de todo.

Comienza explicando el concepto de seguridad como:
La protección de la información frente a las distintas amenazas al objeto de garantizar el
buen funcionamiento de la organización.
Aportando Confidencialidad, Integridad y Disponibilidad

La ciberseguridad parte de este concepto llevándolo al mundo de la tecnología y la red.
Donde las principales amenazas a enfrentar son:
- Códigos maliciosos
- Spam, Phishing
- Accesos no autorizado, DDoS

## Cifrado y PKI

En este apartado se habla de la identificación digital, los tipos que existen de claves, su uso, ventajas y desventajas de cada uno partiendo de la siguiente teoría que se resume con la siguiente imagen.

![Gráfica para definir el concepto de muy robusto](/Imagenes/muyrobusto.PNG "Gráfica para definir el concepto de muy robusto")

Dentro de esas claves están:
- Simétrica
- Asimétrica
- Combinación de las dos anteriores

Por último se habla de lo que es _una huella digital o Hash_

Por el apartado de PKI (Public Key Infraestructure)

Se define este como una combinación de elementos que permiten cifrar, firmar y conseguir
el no repudio de comunicaciones electrónicas.

Seguidamente te habla de los elementos funcionales de un pki, los tipos que existen, sus características, y una explicación a cada uno de ellos.
Los cuales serían los siguientes:
- Básicos
  - Autoridad de certificación (CA)
  - Autoridad de registro (RA)
  - Almacén de certificados y claves
- Opcionales
  - Autoridad de sellado de tiempo (TSA)
  - Servidor de revocación

Por último te habla de los procedimiento:
- Básicos
  - Emisión de certificado
  - Almacenamiento y uso de certificado
  - Renovación o expiración de certificado
  - Revocación de certificado
- Opcionales
  - Sellado de tiempo

## Netfilter e iptables

En este apartado se define netfilter e iptables como:
Netfilter es un framework de linux que permite interceptar y
manipular paquetes de red.
Iptables es su componente más popular y actúa como cortafuegos.

Se define términos como:
- Firewall o Cortafuegos
- Filtrado de paquetes
- Enmascaramiento NAT y sus tipos
  - Source Nat (SNAT)
  - Destination Nat (DNAT)

Posteriormente se realizan varios ejemplos prácticos de usos de ambas herramientas en un laboratorio usando equipos de Kali Linux, Windows y Ubuntu.
Explicando cómo se crean las reglas, los tipo de cadenas (chain) que existen y explicandolas:
- INPUT
- OUTPUT
- FORWARD
- PREROUTING
- POSTROUTING

Los tipos de tablas: 
- FILTER
- NAT
- MANGLE

Los tipos de acciones:
- MASQUERADE
- DNAT
- SNAT
- ACCEPT
- DROP
- REJECT
- LOG

Explicación y uso de los diferentes parámetros y operadores.

En conclusión en una buena introducción a varios conceptos de seguridad dentro de la red, y el uso de las herramientas iptables y netfilter, de los cuales hay un curso que entra más en profundidad en iptables dentro de openwebinars.

## NAMP Y SHODAN

En este apartado se da una definición de nmap: herramienta
para escanear puertos abiertos, servicios, versiones, sistemas operativos.

Se te explicara sus usos, como se instala y en qué plataformas está disponible su instalación, se realizará prácticas de ejemplos con una kali linux buscando información por ip y puertos, los estados en los cuales puedes encontrarte un puerto (OPEN, CLOSED, FILTERED), descubrir qué servicios están a la escucha detrás de un puerto al equipo al cual estás obteniendo su información.

Por otra parte se te explicara en qué consiste el motor de búsqueda shodan: escanea
distintos tipos de recursos publicados en internet.

Como se usa, tipos de búsquedas con filtros para que sean más concretas, realizando varios ejemplos prácticos.

La idea de este apartado es explicar con estas dos herramientas que el primer paso consiste en la búsqueda de información desde la red, tanto para auditores como para hacker maliciosos.

## Ataques sobre servicios

En este apartado se verá diferentes tipos de ataques a un equipo.

El primero será el de Fuerza bruta el cual consiste en conseguir un par
usuario-contraseña probando gran cantidad de combinaciones hasta conseguir el correcto.

Se te hablara y explicara los dos tipos que existen con sus ventajas y desventajas, los cuales son el de Fuerza Bruta y el de Diccionario.

Se te explicara de donde puedes sacar diccionarios desde repositorios web para realizar esos ataques, también el uso de la herramienta Crunch para crear tus propios diccionarios, definición y uso de la Herramienta Hydra, y por último se realizan algunos ejemplos prácticos en un laboratorio.

El segundo ataque es por medio del SQL Injection el cual es un método de infiltración de código,
ante la falta de validación de campos, en operaciones sobre una base de datos.

En este apartado se hará una breve explicación de lo que es una base de datos por SQL con algunos ejemplos de consultas.
Se explicara para que se usa el Sql inyection y los problemas que este puede provocar como falta de Confidencialidad, Autenticación e Integridad, que tipos de datos se pueden obtener por medio de este ataque, y ejemplos prácticos por medio de sentencias para sacar información de tablas, schemas y usuarios dentro de una base de datos usando para ello un laboratorio con DVWA (Damn Vulnerable Web Application) el cual es un entorno para poder realizar este tipo de pruebas de forma legal para practicar.

El último método usado de ataque es pos XSS (cross site scripting) el cual es un ataque dirigido a
páginas web y consistente en poder inyectar código HTML y Javascript sin que sea validado
para conseguir algún provecho.

Se te explicara el uso de xss, los dos tipos que existen (directa y reflejada), explicando cada uno de ellos, sus ventajas y desventajas. Se realizara varios ejemplos prácticos de ambos tipos mediante script en lenguaje php, estos ejemplos se realizan en formularios, en la propia url, he insertándose en la propia caja donde un usuario debe escribir.

Por último se explicará lo que es una Cookies, su uso y como robarlas.

## Ataques a Nivel de Red

En este apartado lo primero que se da es una introducción a ciertos conceptos que se deben conocer dentro del mundo de las Redes TCP/IP, en donde se explicarán los tipos de capas de este modelo:
- Capa Física
- Capa de Enlace y datos
- Capa de Red
- Capa de Transporte
- Capa de Aplicación
Un resumen de los protocolos que existen en cada capa, principales dispositivos usados en redes como: 
- Switch
- Hub
- Repetidor
- Router
Se explicará el protocolo ARP y su relación con la MAC de la tarjeta de red.
Y por último los tipos de direccionamientos de ip, los privados, públicos,  las ipv4 y las ipv6. 

Los siguientes apartados consisten en diversos ataques a nivel de red

_MAC Flooding_ que consiste en agotar la tabla de MACs de un dispositivo
para provocar un envío a difusión.
Donde se nos explicara el objetivo de esta práctica, como influye en un switch, las consecuencias de ello, un ejemplo de como realizarlo a modo práctico con la herramienta Macof de kali, y que metodo de prevencion se puede usar para prevenir este tipo de ataque.

_MAC Spoofing_ que consiste en suplantar la MAC de un dispositivo dentro de una red para distintos fines.
En este apartado también se explicara en qué consiste el DOS (Denegación de servicios).
Se explicará cómo afecta este ataque a un switch, lo que se trata de conseguir, un ejemplo práctico de cómo ejecutarlo con la herramienta de Macchanger de kali, y por último métodos de prevención frente a este ataque.

_Man in the middle_ que consiste en capturar la información intercambiada entre cliente y servidor ilegítimamente.
Te explicaran el uso y funcionamiento de este ataque, como actúa en la tabla caché ARP, las consecuencias de esto, el uso de ARP spoofing que es necesario para realizar el man in the middle, una prueba práctica de cómo realizarlo y métodos de prevención frente a este ataque.

_DNS Spoofing_ que consiste en crear tramas falsas para envenenar las resoluciones de consultas DNS.
En este apartado lo primero que te explican es que es y en qué consiste el servicio DNS, para poder entender mejor cómo actúa el dns spoofing, su uso y consecuencias como la suplantación de una web para el robo de credenciales, y la demostración de este ataque con un ejemplo práctico.

## Vulnerabilidades y Metasploit

Este apartado en una introducción a metasploit y meterpreter.
Hay un curso donde se entra más en profundidad en el uso de Metasploit en Openwebinar, el cual forma parte de la carrera de Ciberseguridad.

Lo primero es una definición de Metasploit el cual es el framework más
común usado en seguridad informática para tareas de creación o ejecución de exploits.

Acto seguido se te explicara los diferentes tipos de vulnerabilidades:
- De Software
- De hardware
- Red de comunicaciones

Las etapas de las vulnerabilidades explicando cada una de ellas:
- Nacimiento
- Descubrimiento
- Comunicación
- Corrección
- Publicación
- Automatización de la explotación (exploit)
- Muerte

Los diferentes casos según el orden de las etapas antes mencionadas.

Seguidamente se da una introducción a Metasploit, sus usos, utilidades, etc.
También se hace una breve definición de lo que es un Pentester, que básicamente es identificar y obtener información de puertos y servicios.

Se da una descripción de las herramientas auxiliares de metasploit:
- Msfpayload
- Msfencode
- Msfvenom

Descripción de los módulos principales de metasploit y la ruta donde se encuentran:
- Auxiliary
- Encoders
- Exploits
- Payloads

El siguiente apartado consiste en explicar cómo trabajar con metasploit mediante la consola msfconsole.
Y una breve descripción de los principales comando:
- Help
- Search
- Use
- Info
- Show
- Back
- Set & Setg
- Unset & Unsetg
- Run
- Exploit
- Check
- Sessions
- Background
- Save

Seguidamente se realiza un caso práctico donde se explota las vulnerabilidades de un equipo windows 7 con el servicio Badblue con vulnerabilidades conocidas.
En las cuales se explica cómo primero se realiza un escaneo de los puertos y servicios que están activos, una vez encontrado los servicios y sus versiones se busca si tiene vulnerabilidades, encontradas las vulnerabilidades se busca si existen exploit para ellos,  se configura el exploit, una vez preparado el exploit se busca un payload (este es explicado en el curso), y una vez todo listo se ejecuta. 

El último apartado trata sobre Meterpreter uno de los payload más completos de metasploit.
Es en este apartado donde se explica lo que es un payload, la importancia de estos en la post-explotación, los tres tipos que existen de estos con una definición de cada uno de ellos (Single, Stagers, Staged) 

También se habla de los módulos auxiliares con un ejemplo para realizar un ataque de denegación de servicios.

Después se habla en profundidad del payload Meterpreter, definiendo varios de sus comando agrupándolos en tres categorías:
- Core commands
	- Scripts de meterpreter
	- Run
	- bgrun
	- bglist
	- bgkill
	- background
	- migrate
- Stdapi
	- File System Commands
	- Networking Commands
	- System Commands
	- User Interface Commands
	- Webcam Commands
- Priv
  - Elevate commands
  - Password Database Commands
  - Timestamp Commands
Por último se explica el uso del script Winenum el cual realiza gran cantidad de tareas como: listado de programas instalados, volcado de hashes, obtención de información de sus redes.

## Anonimato

El último apartado consiste en cómo un hacker malicioso o incluso un auditor debe mantener el anonimato.
Aquí se explica el uso e instalación de la herramienta TOR (The Onion Router) el cual es una Red compuesta por routers que ocultan la dirección IP origen del usuario.


