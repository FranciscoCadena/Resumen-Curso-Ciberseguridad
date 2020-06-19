# Hacking Web

Este curso se centra en ataques con Sql inyection, el xss, robo de sesiones y tipos de ataques de ficheros.

Lo primero del curso es la definición del hacking web como la búsqueda y explotación de
vulnerabilidades de seguridad en sistemas o redes.

Y explicar los tipos de hacker que existen.
- White hat
- Black hat
- Grey hat

## Inyecciones de código

La primera parte de este apartado consiste en explicar en qué consiste el SQL inyection, el problema que acarrea la sentencia logia 1=1, y como de manera práctica mediante un equipo que el profesor ya tiene montado con una base de datos realiza una sentencia sql inyection para sacar un usuario mediante la sentencia ‘999’ or ‘1’ = ‘1’ .
Más adelante explica como sacar los artículos de una base de datos, incluso modificar los valores de estos como el precio. El único problema es que casi todos los apuntes que aporta están en un repositorio de github por lo que hay que intentar copiar las sentencias viéndola directamente por el video o ir directamente a su repositorio https://github.com/OpenWebinarsNet/cursoHackingWeb.

La siguiente parte de este apartado es el uso de XSS el cual también se ve en el curso de Ethical Hacking, con mejores ejemplos y mejor explicado.
Donde define lo que es el XSS, que es lo que ocurre cuando un usuario lo ejecuta desde un formulario.
Seguidamente te hace una breve explicación de los dos tipos de xss que hay (almacenado y el reflejado). 
Por último realiza un ataque de ejemplo con el xss tanto reflejado como almacenado, usando un script en un formulario, en donde al hacer clic en este formulario nos puede redirigir a otra página, a la vez que robamos la sesión de ese usuario que a cliqueado.

## Ficheros

En este apartado se nos explica en qué consiste el _Unrestricted File Upload_, las consecuencias de tener un formulario sin restricciones frente a un fichero como límite de tamaño o extensiones.
Posibles ataques que se pueden realizar a estos formularios sin restricciones:
- Fichero malicioso ejecutable en servidor (.jsp, .php, etc.).
- Fichero de gran tamaño.
- Fichero con nombre/ruta sensible (sobreescribe fichero de
sistema).
Y posibles medidas para prevenir estos ataques.
- Restringir la extensión y tipo de fichero.
- Restringir tamaño máximo de fichero.
- Sanear nombre de fichero.
- Descargar fichero y no abrir desde el servidor.

Más adelantes realiza un ejemplo práctico en el cual sube a un formulario un fichero en lenguaje php el cual contiene una shell, gracias a eso después de subir el fichero puede ejecutar la shell desde la url y navegar por el formulario consultando todo lo que haya en el servidor.

La siguiente parte de este apartado nos habla del _Local File Inclusion_ donde prácticamente se manipula la ruta de un fichero del servidor para acceder a otro de manera fraudulenta.
Después de explicar esto nos muestra un ejemplo práctico donde desde la url del formulario observa la ruta de un  fichero, y luego modifica la ruta de ese fichero escribiendo por ejemplo _../../../../../etc/password_ con ello consigue acceder al fichero donde se almacena todas las contraseñas del servidor.

## Robo de Sesiones

En este apartado se explica en qué consiste el _Session prediction_, los problemas de este y algunas medidas para prevenirlo:
- ID de sesión creado en el servidor.
- Único.
- Aleatorio.
- Encriptado.
- Tiempo de expiración.
- Bonus: solicitar contraseña de usuario actual para poder cambiarla por una nueva.

Seguidamente realiza un ejemplo práctico de este ataque con la herramienta _ZAP_ descargada de la página __OWASP__ en el cual captura la cookie de la sesión de un usuario que se registra, el cual es _user1_ una vez capturado modifica el user1 por user2  y entra como user2, este es un problema de tener una sesión  fácil de deducir por ser secuencial en vez de aleatorio.

La siguiente parte del curso te explica qué es y en qué consiste un ataque de fuerza bruta, esto se puede ver también en el curso de Ethical Hacking. 
Algunas de las medidas que explica para prevenir esto son:
- Contador de reintentos.
- Captcha.
- Bloqueo de usuario.

Después de explicar este ataque muestra un ejemplo práctico de este ataque usando la herramienta _Apache Jmeter_ y un password de tipo fecha, donde el ataque de fuerza bruta lo realiza con un script.
## Accesos ilegales
 
En este apartado se explica primero en qué consiste el _Parameter Tampering_ el cual prácticamente consiste en manipular datos entre cliente y servidor.
También da algunos consejos para prevenir esto como:
- Validaciones en el servidor.
- No enviar datos innecesarios.

Después de la explicación realiza un caso práctico de este ataque usando la herramienta _ZAP_ en donde se modifica el valor de un artículo a la hora de comprarlo.

El último apartado se explica el control inseguro de los roles, donde prácticamente un usuario sin permisos consigue acceder a un directorio donde solo un administrador puede acceder, para prevenir esto puedes realizar:
- Comprobaciones de permisos en servidor.
- Validar en servidor cada acción del usuario.

Una vez explicado se realiza un caso práctico desde un foro, en el cual se accede con un usuario normal y un usuario con permisos de administración, se observa la url de ambos, entonces cuando se accede con el usuario sin permisos se escribe en la url la ruta del usuario que tiene permisos de administrador y consigue entrar este usuario que no tiene permisos.

[Inicio](https://franciscocadena.github.io/Resumen-Curso-Ciberseguridad/)

