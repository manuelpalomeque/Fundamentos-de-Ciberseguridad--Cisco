## 1) Ejecutar Nmap:

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

D) Detectar las versiones que puede usar para investigar vulnerabilidades, mediante el comando -sV.

    cisco@labvm:~$ sudo nmap -sV localhost
    [sudo] password for cisco: 
    Starting Nmap 7.80 ( https://nmap.org ) at 2022-01-19 13:48 UTC
    Nmap scan report for localhost (127.0.0.1)
    Host is up (0.0000020s latency).
    Other addresses for localhost (not scanned): ::1
    Not shown: 997 closed ports
    PORT    STATE SERVICE VERSION
    22/tcp  open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
    23/tcp  open  telnet  Linux telnetd
    631/tcp open  ipp     CUPS 2.3
    Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
    
    Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
    Nmap done: 1 IP address (1 host up) scanned in 6.45 seco

## 2) Usar privilegios administrativos con Nmap:
a) Escanear los puertos UDP de la computadora:

    cisco@labvm:~$ sudo nmap -sU localhost
    [sudo] password for cisco: 
    Starting Nmap 7.80 ( https://nmap.org ) at 2022-01-19 14:17 UTC
    Nmap scan report for localhost (127.0.0.1)
    Host is up (0.0000020s latency).
    Other addresses for localhost (not scanned): ::1
    Not shown: 998 closed ports
    PORT     STATE         SERVICE
    631/udp  open|filtered ipp
    5353/udp open|filtered zeroconf
    
    Nmap done: 1 IP address (1 host up) scanned in 1.34 seconds


## 3) Capturar claves SSH:

a) Iniciar un escaneo de secuencias de comandos para capturar las claves SSH para el sistema host:

    cisco@labvm:~$ nmap -A localhost
    Starting Nmap 7.80 ( https://nmap.org ) at 2022-01-19 14:02 UTC
    Nmap scan report for localhost (127.0.0.1)
    Host is up (0.000027s latency).
    Other addresses for localhost (not scanned): ::1
    Not shown: 997 closed ports
    PORT    STATE SERVICE VERSION
    22/tcp  open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
    | ssh-hostkey: 
    |   3072 56:68:77:00:41:7f:50:17:5b:73:82:36:47:c4:bc:2d (RSA)
    |   256 0e:52:78:ba:08:2a:df:e5:be:1b:07:a7:98:3a:c8:50 (ECDSA)
    |_  256 f7:9e:03:10:96:94:cc:f4:4f:2a:f2:7c:6a:37:c1:6f (ED25519)
    23/tcp  open  telnet  Linux telnetd
    631/tcp open  ipp     CUPS 2.3
    | http-robots.txt: 1 disallowed entry 
    |_/
    |_http-server-header: CUPS/2.3 IPP/2.1
    |_http-title: Home - CUPS 2.3.1
    Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
    
    Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
    Nmap done: 1 IP address (1 host up) scanned in 13.47 seconds

b)¿Cuáles son los valores de las claves de host SSH?

    | 3072 56:68:77:00:41:7f:50:17:5b:73:82:36:47:c4:bc:2d (RSA)
    | 256 0e:52:78:ba:08:2a:df:e5:be:1b:07:a7:98:3a:c8:50 (ECDSA)
    |_ 256 f7:9e:03:10:96:94:cc:f4:4f:2a:f2:7c:6a:37:c1:6f (ED25519)


c)¿Cómo usaría un atacante esta información?

d)¿Cómo podría evitar que el atacante cibernético robe la información clave?