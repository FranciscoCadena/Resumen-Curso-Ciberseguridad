# Hacking con Buscadores

Este curso es muy práctico donde prácticamente el profesor deja las búsquedas avanzadas para que uno pueda probar desde su buscador

Lo primero que nos enseña el curso es a diferenciar lo que es un motor de búsqueda web “algoritmo que ejecuta nuestras búsquedas en Internet” de lo que es un navegador web “ ejecutan software que hace uso de los motores de búsquedas”.

Seguidamente nos da una explicación de los tres motores de búsqueda que se usarán durante el curso:
- Shodan
- Google
- Bing

## Google robots

En este apartado lo primero que nos explica es que son los archivos __robots.txt__ “es un archivo de texto sin formato en el cual se configuraran las páginas web cara a los rastreadores de google, en los archivos”, los dos tipos de etiquetas que nos encontraremos dentro de ellos (Allow, Disallow) y que hace cada una de esas etiquetas.

Seguidamente nos realiza un ejemplo de búsqueda avanzada también denominadas como __Dorks__ para sacar los archivos robots.txt de algunas páginas como vodafone y apple.

En los siguientes apartados se nos muestra toda la información que se puede sacar de los archivos robots.txt para preparar un ataque, en donde se pueden ver rutas a diversos directorio los cuales si no están protegidos al tu escribirlos en las url pueden incluso acceder a inicios de sesiones o a directorios donde están los password de usuarios registrados.

También nos deja varios Dorks para poder practicar nosotros desde el motor de búsqueda de Google, como por ejemplo:

- inurl:robots.txt "/administrator" ext:txt
- inurl:"/robots.txt" + "Disallow: passwords.txt"
- inurl:robots.txt filetype:txt "/INSTALL.mysql.txt"
- inurl:robots.txt filetype:txt "/wp-admin"

## Hacking con Google

En este apartado se nos explica los métodos de búsqueda avanzados usando Google, y algunos de sus operadores lógicos para filtrar las búsquedas y obtener resultados más precisos de nuestras búsquedas, algunos de estos buscadores son:
- site (Nos buscaría dominios por países)
- inurl (Nos buscaría en la url)
- filetype o ext (Buscaríamos por extensión de archivos)
- intext (Nos buscaría en el texto de la página)
- intitle (nos buscaría en el título de la página)
- “” (nos buscaría exclusivamente lo que metas dentro)

También nos explica la importancia de esta búsqueda para los auditores de seguridad ya que con esta técnica pueden buscar desde directorios desprotegidos, hasta logs de sesiones y contraseñas en texto plano.

Por último se realizan varias búsquedas como ejemplo con buscadores lógicos en Google dejando algunos dorks para nosotros poder probarlos como:
- index.of.dcim (buscaríamos archivos indexados en páginas web de dispositivos de almacenamiento de teléfonos móviles)
- site:es filetype:pdf intext:economia (buscaríamos en dominios de España, documentos pdf donde en su texto contenga la palabra “economía”)
- intext:”Index of /“ +password.txt (Contraseñas en texto plano)
- filetype:sql password (contraseñas de bases de datos Sql)
- “you have an error in your sql syntax” inurl:/events.php?id= (búsqueda de errores en bases de datos Sql)

## Hacking con Bing

Este apartado es prácticamente idéntico al anterior con Google donde nos enseñaran los operadores lógicos de Bing para filtrar nuestras búsquedas, encontrar archivos robot.txt y búsquedas avanzadas de Dorks.
La idea es usar diversos motores de búsqueda para contrastar información y ver los diversos resultados que nos dan cada uno de estos.
Prácticamente todo el cursos será práctico donde  se realizarán varias búsquedas dándonos las sentencias para poder probarlos nosotros.

Como operadores lógicos de bing están algunos como:
- filetype o ext (Buscaríamos por extensión de archivos)
- contains (Permite buscar enlaces a ficheros con una extensión concreta)
- intitle (este operador al igual que en Google nos buscará en el título de la página)
- domain (nos buscara toda la información de un dominio en concreto)
- feed (nos buscará en canales rss de las páginas)

Como ejemplos de dorks tenemos:
- contains:rdp intitle:”index.of” (nos buscará en el título archivos indexados de rdp que son Escritorios remotos)
- domain:uned.es filetype:pdf (nos buscará en el dominio de la uned.es archivos con extensión PDF)
- feed:hacking loc:es (nos buscará canales RSS relacionados con el hacking en dominios de España)
- intitle:index.of.* loc:es (nos buscará en el título de la página archivos indexados en dominios de España)

## Hacking con Shodan

En este apartado se nos explicara detalladamente en qué consiste este buscador, lo potente que es, los riesgos que conlleva puesto que nos da muchísima información de todos los sistemas conectados a internet y servicios que pueden ser vulnerables o no, todo expuesto al público, por tanto es una herramienta muy útil tanto para ciber delincuentes como para auditores de seguridad.

También se nos mostrará algunos de sus operadores lógicos como:
- country (filtraremos por países)
- port (nos filtra por puertos)
- title (nos buscará por cabeceras)
- os (nos buscará por sistema operativo)

Y se realizan varios ejemplos de búsquedas avanzadas como.
- Minecraft Server port:25565
- product:MySQL
- port:5432 PostgreSQL
- Android Webcam Server -Authenticate

## Herramientas automatizadas

En este apartado se nos explicara sobre algunas herramientas que realizan las búsquedas avanzadas anteriormente vistas en el curso pero de manera automática, con lo que nos ahorra mucho tiempo, tan solo hay que configurar que tipo de búsqueda quieres realizar y en qué motores de búsqueda quieres realizar la búsqueda y ya se encarga la herramienta de hacerla por ti, mostrándote todos los resultados, estas herramientas se encuentran tanto en entorno gráficos como en consola CMD, durante esta parte del curso se hablará detalladamente de varias de estas herramientas, explicando sus principales usos y funciones, todo de manera práctico.

Las herramientas que se ven en el curso son:
- Foca forensic
- Snitch
- Sqli Hunter
- Bingoo

## Metadatos

En este apartado del curso se nos hablará de la herramienta __Exiftool__ y de su entorno gráfico __PyExifToolGui__, las cuales su función principal es la obtención y modificación de metadatos.

Se explicara como instalarlas, como trabajar con ellas capturando de manera práctica fotografías sacadas de internet y modificando algunos de sus valores como la longitud y latitud de donde fueron realizadas estas fotos.

También se nos explicara en qué son los datos Exif, mostrándonos ejemplos de ellos al capturar imágenes y poder ver todos los datos que estas contienen, como ver con que dispositivo se tomó la foto, el día y la hora, el formato de la imagen y mucha más información.


