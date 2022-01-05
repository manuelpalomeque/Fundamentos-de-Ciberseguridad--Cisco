# 1) Ejecutar Nmap:

a) Ejecutar un escaneo básico contra este sistema:

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

b)¿Qué puertos TCP están abiertos?

    22/tcp  open  ssh
    23/tcp  open  telnet
    631/tcp open  ipp

c)Proporcione una descripción del servicio asociado con cada puerto abierto.
    
*22 ssh (Secure Shell):*  sirve para acceder a máquinas remotas a través de una red y manejar por completo el sistema 
mediante un intérprete de comandos. También podremos copiar datos de forma segura

*23 telnet :*  sirve para establecer conexión remotamente con otro equipo por la línea de comandos y 
controlarlo. Es un protocolo no seguro ya que la autenticación y todo el tráfico de datos se envía sin cifrar.

*631 ipp (Internet Printing Protocol):*  es un sistema basado en estándares para permitir la impresión remota desde un
PC a cualquier impresora accesible.
