# Snort

Este curso al igual que el de metasploit solo va centrado a snort donde se habla y explica bastante en profundidad sobre esta herramienta de detección de intrusos de manera practica, pero al ser una herramienta tan compleja no se puede abordar todo lo que se puede realizar con ella, con lo que es una introducción y explicación de varios conceptos básicos y su utilización.

Lo primero que nos explicara el curso es que es Snort, para que se usa y sus funciones.
Se explicara como instalarlo desde repositorios y desde la fuente.

Se explica varios detalles sobre su fichero de configuración, en el cual se irán insertando las reglas creadas por nosotros.
Se explicara la sintaxis y creación de varias reglas mediante varios casos prácticos, también se mostrara algunas paginas de las cuales poder descargar reglas ya configuradas para varios casos.

Se mostrara las diversas salidas de eventos de snort, ya sea por consola, por creación de ficheros de texto plano o mediante los syslog.

Se nos mostrara el funcionamiento de Snort y los problemas que tiene al trabajar con un solo hilo o Thread, de hay que trabaje con otras herramientas como Unified el cual le ayudara a recoger los paquetes y alertas y registrarlos en una base de datos.
Se explicara en que consiste detalladamente el uso de _Unified2_, sus usos y formato.
Tambien se hablara de otra herramienta que ayuda a snort al igual que unified 2 el cual se llama _Banyard2_.

Se nos hablara del modulo DAQ y su uso con snort, el cual principalmente es un intermediario entre snort y la obtención de paquetes.

Tambien se nos hablara de la obtencion de paquetes mediante el protocolo PCAP, y posteriormente del nuevo metodo llamado AF_Packet.

Se nos explicara en que consiste un decodificador y como crear reglas con el.

El ultimo apartado del curso, trata sobre los preprocesadores que trabajan con snort.
En el cual se hablara sobre los mas comunes entre ellos, se explicara el uso de cada uno y como trabajar con ellos.
- Frag3
- Stream5
- Reputation: dentro de este preprocesador se hablara sobre las listas blancas y negras
- Http
- PortScan
