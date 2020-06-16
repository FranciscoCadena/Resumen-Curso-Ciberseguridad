# Desarrollo Seguro

Este curso es bastante teórico, con algunas prácticas y con poca información documentada, solo algunos pdf con muy poco datos, teniendo que ver los videos varias veces para enterarte de todo y cogiendo apuntes.

## Ciclo de desarrollo seguro de software

La primera parte del curso nos da una introducción sobre qué es la seguridad, la importancia de esta, lo importante que es hoy en día la información, el ciclo de vida que tiene y algunos ejemplos con noticias reales de lo que ocurre cuando no se presta atención a la seguridad, y se obtiene información relevante y confidencial.

Este apartado está subdividido en los siguientes apartados:
- Requisitos
- Arquitectura y diseño
- Implementación
- Testeo
- Despliegue
- Mantenimiento

En los cuales en cada uno de esos apartados nos explicara las fases en que consiste cada uno de ellos y las medidas de seguridad que tenemos que abordar en cada uno de ellos. 


## Seguridad en el Desarrollo

En este apartado ya si se realizan algunas prácticas de ejemplo, donde se nos hablará de Sql inyection, XSS, Criptografía y el Buffer Overflow.

En el apartado de validación de entradas se nos habla principalmente del riesgo de un ataque por sql inyection, aportandonos medidas de seguridad para prevenir estos ataques, en el cual se explican métodos para la validación de fichero y entradas.
La práctica la realiza sobre un servicio vulnerable aportado por la web de __OWASP__ llamado _bWAPP_, en este realiza varias sentencias de sql inyection en donde va sacando información de la base de datos, los schemas y tablas que hay dentro de esa base de datos, también saca el nombre de las tablas, las columnas de cada tabla, los usuarios registrados en la base de datos y sus id y password de cada usuario.

En el apartado de codificación de salida se centra en el ataque por XSS, y que medidas de seguridad hay que tomar en cuenta en la codificación de salidas.

En la parte práctica vuelve a usar la aplicación _bWAPP_ donde se ejecuta un script para poder sacar y obtener datos del usuario como su cookie, para luego poder robarle la sesión.

En el apartado de Criptografía nos habla de la importancia de esta a la hora de cifrar la información, que medidas de seguridad hay que tener en cuenta, que tipo de archivos cifrar, también se nos habla de diferentes módulos criptográficos y la importancia de la aleatoriedad, y que no haya secuencialidad.

La práctica la realiza desde la web OWASP yendo esta vez a la aplicación _Multillidae II_ en la cual mediante sql inyection saca las contraseñas de los usuarios de una base de datos y estas no están cifradas.

En el apartado de __Buffer overflow(Desbordamiento de buffer)__ se nos habla de este ataque, las repercusiones históricas que tuvo el ataque, como actúa en un  sistema y que medidas adoptar para prevenirlo.

En el caso práctico nos muestra un script el cual realiza este ataque, lo realiza un equipo virtualizado con docker, en el cual al ejecutarlo nos muestra los resultados de este ataque pudiendo entrar a funciones secretas del sistema.

## Seguridad en los procesos y procedimientos

La primera parte de este apartado nos hablará de la importancia de la autenticación de los usuario y el manejo de las contraseñas, en donde se nos dará varias medidas y consejos de seguridad que implementar para asegurar la autenticación.

La práctica de esto la realiza con la aplicación multillidae II, en donde se crea un usuario, luego usa la herramienta _Burp Suite Free Edition_ para capturar la sesión de un usuario con permisos de root, y modificando un valor que en principio está encriptado pero de manera secuencial va probando diversas combinaciones hasta conseguir la id de sesión, con eso ya puede hacer que un usuario que no tenga permisos de root, consiga tenerlos o acceder como root directamente.

En el apartado de manejo se sesiones se nos explicará la importancia de las sesiones y que medidas adoptar para asegurarlas.

La práctica la realiza mediante la aplicación _WebGoat_  donde la aplicación pone un desafió que es registrarse con un usuario en concreto, el procedimiento es parecido al realizado en la práctica anterior donde con la herramienta _burpsite_ capturar la cookie y en concreto un código cifrado, ese código lo lleva a la página de PHP encode donde comprueba el tipo de encriptado que trae, hasta poder sacar tanto el nombre del usuario como la contraseña.
Es una práctica interesante y algo difícil de explicar.

En el apartado de manejo de errores se nos habla de la importancia de estos métodos para asegurar el manejo de errores y los logs para que nadie de fuera pueda verlo, porque al fin y al cabo esos errores son posibles vulnerabilidades, también se da algunas pautas sobre qué tipos de datos y información guardar en los logs.

La práctica se realiza desde la aplicación de WebGoat, en donde el objetivo es registrarse solo con la ID del usuario sin necesidad de la contraseña, para corroborar el error que existe.

## Seguridad en la configuración del entorno

Este último apartado del curso se nos hablará de:
- Control de acceso
- Control de datos
- Seguridad de comunicaciones
- Configuración del sistema
- Seguridad en Base de datos
- Manejo de fichero
- Manejo de memorias

Donde al igual que en los anteriores apartados se nos hablará de la importancia de cada uno de ellos, los riesgos que trae consigo si no tomamos las debidas precauciones, y varias medidas a adoptar en cada uno de ellos para asegurarlos.

Lo más interesante de este apartado son las prácticas de cada uno donde se nos muestra los problemas que pueden suceder si no se toma las medidas pertinentes.

