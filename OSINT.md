# OSINT

Curso con videos bastante cortos pero concretos donde se verán ciertos temas ya vistos en otros cursos de seguridad como el hacking con buscadores donde hay un curso centrado en esto, también se hablará de los metadatos y herramientas para obtener información de ellos y modificarlos, pero se abordaron temas nuevos. En donde lo principal del curso será en contrastar la información que se difunde por las redes y ver su fiabilidad y credibilidad con el uso de diversas herramientas e investigación.

## OSINT

En este primer apartado del curso se nos dan conceptos sobre lo que entendemos por _ciberinteligencia y fuente abierta_.

También se nos hablará de cuatro términos diferentes y a la vez relacionados:
- OSINT (Open Source Intelligence): Inteligencia en fuentes abiertas
- HUMINT (Human Intelligence): Inteligencia de fuentes humanas
- SOCMINT (Social Media Intelligence): Inteligencia en RRSS
- CYBINT (Cyber Intelligence): Inteligencia en el ciberespacio

Se nos hablará del ciclo _INCIBE_ y sus 6 fases que lo componen.
- Requisitos
- Fuentes de información
- Adquisición
- Procesamiento
- Análisis
- Inteligencia

De los problemas que trae hoy en día el exceso de información para poder almacenarla, la fiabilidad de las fuentes y la información que se encuentra hoy en día por internet y cómo esa información puede ser falsa o errónea de manera malintencionada.

A raíz de la información se nos hablará del tipo de clasificación de esta según sus fuentes
Donde la fiabilidad de la fuente se categoriza desde la A-F de mayor a menor fiabilidad
Y lo mismo con la Credibilidad del contenido con rangos del 1 al 6 de mayor a menor.

Por último se nos hablará del papel que desempeña el factor humano en todo esto y su importancia.

## Hacking con buscadores

En donde se nos explicara que es el Google Hacking, los distintos tipos de metabuscadores,  cuales son los principales Dorks o búsquedas avanzadas usados en Google

También se no dará una breve explicación de otros buscadores usados como bing, y que dependiendo de la información que busques merece la pena usar uno u otro como por ejemplo:
- BAIDU: Motor de búsqueda chino
- YANDEX: Motor de búsqueda ruso
- DUCKDUCKGO: Centrado en privacidad, no rastreo de usuarios

Se nos enseñara a saber realizar búsquedas inversas de imágenes, para cotejar información y saber si la información que se está dando es falsa, real, o sacada de otro sitio, para ello se explicará de manera práctica cogiendo una imagen y usando la herramienta _TinEye_, y también usando los motores de búsqueda de Google y Yadex, con ellos al subir una imagen nos mostrará en todos los sitios donde aparece esta imagen o alguna parecida.

Se nos explicara qué son los buscadores tecnológicos donde el más usado es __Shodan__, para buscar información de equipos conectados a la red y cómo filtrar las búsquedas con diversos operadores, a parte se nos hablará de otros buscadores tecnológicos parecidos a shodan como son __ZOOMEYE__ el cual es Chino y __MRLOOQUER__ desarrollado por expertos en ciberseguridad españoles.

Se nos explicara lo que es la parte superficial de internet, la parte profunda y la parte obscura, y los buscadores que hay para ellos como:
- AHMIA.FI
- TORCH
- GRAMS
- CANDLE

## Metadatos

En este apartado se nos dará una definición de lo que son los metadatos y su importancia por la cantidad de información que traen y que desconocemos.

También se nos explicara de manera práctica cómo sacar esta información con herramientas como _ExifTool_ o _Foca_ realizando ejemplos parecidos a los vistos en el curso de Hacking con Buscadores. Donde se nos enseñara a usar ambas herramientas, donde descargarlas e instalarlas.

## Herramientas

Lo primero que veremos en este apartado será preparar un laboratorio para realizar una investigación OSINT, donde se usará virtualbox y como imagen un SO especialmente diseñado para esta actividad, creado por un ex-agente del FBI llamado Michael Bazzell, la cual podemos descargar desde su web https://inteltechniques.com/buscador/index.html

Se nos dará algunos comandos para trabajar con ellas, y se nos dirá algunas de las herramientas que ya trae por defecto este SO como:
- TOR Browser (navegador DeepWeb)
- Maltego (herramienta de minería de datos en OSINT)
- Creepy (herramienta de geolocalización en Twitter)
- theHarvester (herramienta de obtención de información pública)
- Tinfoleak (herramienta enfocada a la extracción de información en Twitter)

Seguidamente se nos explicara tanto de forma teórica como práctica el uso de _Open Source Research Framework_ (OSRFramework) este es un paquete de aplicaciones para recopilar información de fuentes abiertas.
Ya viene instalado por defecto en la imagen de IntelTechniques, pero podemos instalarla y ver varias de sus funciones desde su fuente en github https://github.com/i3visio/osrframework
Se nos explicara a usar el osrframework enseñándonos y explicando su gran cantidad de funcionalidades como:
- usufy.py: 
- alias_generator.py: 
- mailfy.py:
- searchfy.py: 
- phonefy.py: 
- entify.py: b
- domainfy.py: 

Se nos hablara de la herramienta __Maltego__ la cual se emplea en las investigaciones en línea para
encontrar relaciones entre piezas de información de diversas fuentes ubicadas en Internet .
De manera práctica nos mostrará el diseño de esta herramienta y algunos de sus usos para buscar dominios, personas, alias, email, etc.

Se nos hablará de los distintos repositorio de OSINT que existe, mostrándonos de manera gráfica varias páginas con estos contenidos y sus respectivos enlaces.
- IntelTechniques: https://inteltechniques.com/menu.html
- NetBootCamp: custom searchs forms: https://netbootcamp.org/osinttools/
- OSINTFramework: http://osintframework.com/
- Ciberpatrulla: https://ciberpatrulla.com/links/

Nos mostraran diferentes herramientas Whois donde se recaba información de registros, dominios y direcciones ip, entre las herramientas de las cuales se hablan están:
- DomainTools
- MXTollBox
- ViewDNS.info
- IP2Location

## Monitorización en OSINT

En este apartado se nos hablara y explicara las diversas herramientas para la monitorización de osint.
Donde se explicará cómo instalarlas, y usarlas con ejemplos, entre estas herramientas están :
- TweetDeck
- Twitonomy

El último apartado será como crear servicios de alertas por email para monitorizar sitios webs, blogs, noticias, etc.
Algunas de estas herramientas que serán vistas son:
- Google Alerts
- TalksWalker Alerts

## Privacidad y Anonimato

En este apartado se hablará sobre la creación de una identidad anónima digital a la hora de realizar una ciber investigación. Qué pasos hay que seguir, como definir perfiles sociales, números de teléfono, emails, etc todo de manera ficticia.

También se nos explicara algunas herramientas que ya realizan algunas de estas tareas como:
- FakeNameGenerator
- ProtonMail

Por último se explica medidas para enmascarar la identidad, es decir la ubicación e ip que tenemos.
Como por ejemplo realizar la investigación desde una máquina virtual, navegar con TOR, usar Proxy o VPN, etc.

[Inicio](https://franciscocadena.github.io/Resumen-Curso-Ciberseguridad/)

