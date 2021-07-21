## 1) Establecer una VPN de acceso remoto:

1-b) Que direccion IP tiene asignada la laptop?

    C:\>ipconfig
    
    Wireless0 Connection:(default port)
    
    Connection-specific DNS Suffix..: 
    Link-local IPv6 Address.........: FE80::20C:CFFF:FEA7:C963
    IPv6 Address....................: ::
    IPv4 Address....................: 192.168.0.12
    Subnet Mask.....................: 255.255.255.0
    Default Gateway.................: ::
    192.168.0.5
    
    Bluetooth Connection:
    
    Connection-specific DNS Suffix..: 
    Link-local IPv6 Address.........: ::
    IPv6 Address....................: ::
    IPv4 Address....................: 0.0.0.0
    Subnet Mask.....................: 0.0.0.0
    Default Gateway.................: ::
    0.0.0.0

La direcion es: 192.168.0.12

1-d) Cual es la direccion IP del tunel?

    C:\>ipconfig /all
    
    Wireless0 Connection:(default port)
    
    Connection-specific DNS Suffix..: 
    Physical Address................: 000C.CFA7.C963
    Link-local IPv6 Address.........: FE80::20C:CFFF:FEA7:C963
    IPv6 Address....................: ::
    IPv4 Address....................: 192.168.0.12
    Subnet Mask.....................: 255.255.255.0
    Default Gateway.................: ::
    192.168.0.5
    DHCP Servers....................: 192.168.0.5
    DHCPv6 IAID.....................: 
    DHCPv6 Client DUID..............: 00-01-00-01-1D-49-DC-42-00-0C-CF-A7-C9-63
    DNS Servers.....................: ::
    10.2.0.125
    
    Bluetooth Connection:
    
    Connection-specific DNS Suffix..: 
    Physical Address................: 0004.9AD8.E7C2
    Link-local IPv6 Address.........: ::
    IPv6 Address....................: ::
    IPv4 Address....................: 0.0.0.0
    Subnet Mask.....................: 0.0.0.0
    Default Gateway.................: ::
    0.0.0.0
    DHCP Servers....................: 0.0.0.0
    DHCPv6 IAID.....................: 
    DHCPv6 Client DUID..............: 00-01-00-01-1D-49-DC-42-00-0C-CF-A7-C9-63
    DNS Servers.....................: ::
    10.2.0.125
    
    Tunnel Interface IP Address.....: 172.18.1.150

La direcion del tunel VPN es: 172.18.1.150

    Client IP: 172.18.1.150
    
    Tunnel Interface IP Address.....: 172.18.1.150

2-c) Ingresé el comando enable seguido del comando show crypto isakmp sa. Este comando mostrará asociaciones de 
seguridad IPsec activas.

    DC_Edge-Rtr1#enable
    DC_Edge-Rtr1# show crypto isakmp sa
    IPv4 Crypto ISAKMP SA
    dst src state conn-id slot status
    10.1.0.11 10.0.0.2 QM_IDLE 1051 0 ACTIVE
    
    
    IPv6 Crypto ISAKMP SA
    
    
    DC_Edge-Rtr1#

¿Qué estado se muestra en la salida del comando?
ACTIVE

¿Qué dirección IP de destino aparece en la salida y a qué dispositivo se asigna esta dirección?
10.1.0.11, que es la dirección IP de la interfaz G0/0 de Internet del enrutador Cafe.

3-b) Conecte con el servidor ftp y use de credenciales: usuario: remote contraseña: ciscorocks

    C:\>ftp 172.19.0.3
    Trying to connect...172.19.0.3
    Connected to 172.19.0.3
    220- Welcome to PT Ftp server
    Username:remote
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>

3-c) usar el comando dir para ver que archivos estan en la carpeta

    ftp>dir
    
    Listing /ftp directory from 172.19.0.3: 
    0 : PTsecurity.txt 92

3-d) usé el comando get para descargar el archivo y luego cerre la sesion del servidor

    ftp>get
    remote filename not specified
    ftp>get PTsecurity.txt
    
    Reading file PTsecurity.txt from 172.19.0.3: 
    File transfer in progress...
    
    [Transfer complete - 92 bytes]
    
    92 bytes copied in 0.047 secs (1957 bytes/sec)
    ftp>quit
    
    221- Service closing control connection.
    C:\>

3-f) Abrir el archivo PTsecurity.txt y ver el contenido:

    Congratulations! You have successfully downloaded this file from the Data Center FTP server.

## 2) Capturar y examinar el tráfico de la red:

2-b) El comando que use para conectar con el servidor telnet:

    C:\>telnet 10.0.0.2
    Trying 10.0.0.2 ...OpenPrivate network. No unauthorized access.
    
    
    User Access Verification
    
    Username:

2-c) primer resultado del paquete telnet capturado:

    TELNET DATA:Private network. No unauthorized access. User Access Verification Username: 

2-d) El tipo de trafico que se captura cuando intentamos conectar al servidor FTP:

ICMP se genera porque no se puede acceder al servidor FTP. 
Detalles:
ICMP:

    TYPE:0x03 

El tipo ICMP es 3 para Destino inalcanzable

    CODE:0x01 

El código es 1 para host inalcanzable.

3-a) Al reconectarse a la VPN el trafico capturado es:

ISAKMP, que es usado para establecer el tunel VPN
 
3-c) el trafico que captura cuando se hace ping al servidor FTP es:

ISAKMP e IPsec. El tráfico ICMP está oculto dentro del túnel IPsec seguro.

3-d) el trafico que captura cuando se conecta al servidor FTP es:

ISAKMP e IPsec. El tráfico FTP está oculto dentro del túnel IPsec seguro.

3-e) Del analisis del paquete ISAKMP, se concluye que el puerto que se esta usando es el 500

    DESTINATION PORT:500 

