# 1) Ejecutar Nmap:

A) Ejecutar un escaneo básico contra este sistema:

    cisco@labvm:~$ nmap localhost
    Starting Nmap 7.80 ( https://nmap.org ) at 2022-01-18 23:54 UTC
    Nmap scan report for localhost (127.0.0.1)
    Host is up (0.000026s latency).
    Other addresses for localhost (not scanned): ::1
    Not shown: 997 closed ports
    PORT    STATE SERVICE
    22/tcp  open  ssh
    23/tcp  open  telnet
    631/tcp open  ipp

Los resultados son un escaneo de los primeros 1024 puertos.

B) ¿Qué puertos TCP están abiertos?

    22/tcp  open  ssh
    23/tcp  open  telnet
    631/tcp open  ipp

C) Proporcione una descripción del servicio asociado con cada puerto abierto.
    
*22 ssh (Secure Shell):*  sirve para acceder a máquinas remotas a través de una red y manejar por completo el sistema 
mediante un intérprete de comandos. También podremos copiar datos de forma segura

*23 telnet :*  sirve para establecer conexión remotamente con otro equipo por la línea de comandos y 
controlarlo. Es un protocolo no seguro ya que la autenticación y todo el tráfico de datos se envía sin cifrar.

*631 ipp (Internet Printing Protocol):*  es un sistema basado en estándares para permitir la impresión remota desde un
PC a cualquier impresora accesible.

D) Investigue las vulnerabilidades asociadas con cada uno de estos puertos abiertos.

*Puerto 22 ssh:* 
<li>Buffer Overflow</li>
<li>Ataque de Fuerza Bruta.</li>
<li>Punto de Acceso</li>

Ejemplo:
360 Systems contiene una contraseña predeterminada codificada en la serie del servidor de imágenes. Al iniciar sesión 
en el dispositivo a través del puerto TCP 22, un atacante remoto podría obtener privilegios de root en el sistema para 
modificar o cargar videos para reproducirlos de inmediato y afectar el sistema de transmisión de emergencia en los 
Estados Unidos.
Referencias: [ XFDB-82650 ], [ BID-58338 ], [ CVE-2012-4702 ]

*Puerto 23 telnet:* 

<li>Buffer Overflow</li>
<li>Denegacion de Servicio (DoS)</li>
<li>Ataque de Fuerza Bruta</li>
<li>Punto de Acceso</li>
<li>Posibilidad de sniffer</li>

*Puerto 631 ipp:*
<li>Denegacion de Servicio (DoS)</li>

Ejemplo:
Vulnerabilidad  en la implementación del Protocolo de impresión de Internet (IPP) en CUPS antes de 1.1.19 permite a 
atacantes remotos causar una denegación de servicio a través de ciertas entradas al puerto IPP (TCP 631).
Referencias: [ CVE-2003-0788 ] [ BID-8952 ] [SECUNIA-10123]