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


