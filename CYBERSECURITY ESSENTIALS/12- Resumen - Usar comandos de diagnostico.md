## Parte 1: Recopilar la configuración del dispositivo del usuario final

1-a) ¿Qué dirección IPv4 se muestra para la conexión Wireless0 de la laptop HQ-Laptop-1?

sin conexion inhalambrica:

    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::20A:F3FF:FEE4:EEAA
       IPv6 Address....................: ::
       Autoconfiguration IPv4 Address..: 169.254.238.170
       Subnet Mask.....................: 255.255.0.0
       Default Gateway.................: ::
                                         0.0.0.0
    
con conexion inhalambrica:

    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::20A:F3FF:FEE4:EEAA
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.50.3
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.50.1

1-b) Si la dirección IPv4 está en el rango 169.254.0.0/16, ¿qué método se utiliza para asignar direcciones IPv4?
¿Por qué se le asigna a la computadora portátil una dirección IPv4 en el rango 169.254.0.0/16?

Indica que el dispositivo no pudo obtener la dirección de un servidor DHCP. Por lo tanto, el dispositivo 
se asignó a sí mismo un grupo de direcciones 169.254.0.0/16 utilizado para el direccionamiento IP privado 
automático (APIPA).

1-c) Completar la siguiente tabla:

    Wireless0                   |   IP Addressing Information
    
    Link-local IPv6 Address     |   FE80::20A:F3FF:FEE4:EEAA
    IPv6 Address                |   ::
    IPv4 Address                |   192.168.50.3
    Subnet Mask                 |   255.255.255.0
    Default Gateway             |   192.168.50.1
    DNS Servers                 |   N/A

1-d) ¿Ves una dirección de servidor DNS? Explique.

El comando ipconfig no informa la dirección del servidor DNS

1-e) Utilicé el comando ipconfig/all para ver mas informacion

    C:\>ipconfig /all
    
    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 000A.F3E4.EEAA
       Link-local IPv6 Address.........: FE80::20A:F3FF:FEE4:EEAA
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.50.3
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.50.1
       DHCP Servers....................: 192.168.50.1
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-43-B9-1D-8A-00-0A-F3-E4-EE-AA
       DNS Servers.....................: ::
                                         10.2.0.125
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 00E0.A3A2.D8AA
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0
       DHCP Servers....................: 0.0.0.0
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-43-B9-1D-8A-00-0A-F3-E4-EE-AA
       DNS Servers.....................: ::
                                         10.2.0.125

¿Cuál es la dirección del servidor DNS? 

    DNS Servers.....................: ::
                                         10.2.0.125
    

2-b) Completé la siguente tabla con los datos del pc Net-Admin:

    FastEthernet0           |   IP Addressing Information
    
    Physical Address        |   0001.C910.22D6
    Link-local IPv6 Address |   FE80::201:C9FF:FE10:22D6
    IPv6 Address            |   ::
    IPv4 Address            |   192.168.99.9
    Subnet Mask             |   255.255.255.0
    Default Gateway         |   192.168.99.1
    DNS Servers             |   10.2.0.125

## Parte 2 : Recopilar información sobre dispositivos de red

1-c) Necesitamos identificar la información del dispositivo ascendente ubicada en el ISP. Use el comando show ip route | 
begin Gateway:

    HQ-Edge>enable
    HQ-Edge#show ip route | begin gateway
    HQ-Edge#    show ip route | begin Gateway
    Gateway of last resort is 0.0.0.0 to network 0.0.0.0
    
         10.0.0.0/8 is variably subnetted, 6 subnets, 4 masks
    O       10.0.0.0/29 [110/2] via 10.0.0.49, 00:13:11, GigabitEthernet0/0/0
    O       10.0.0.32/29 [110/2] via 10.0.0.49, 00:13:11, GigabitEthernet0/0/0
    C       10.0.0.48/29 is directly connected, GigabitEthernet0/0/0
    L       10.0.0.50/32 is directly connected, GigabitEthernet0/0/0
    O       10.0.3.0/24 [110/3] via 10.0.0.49, 00:13:11, GigabitEthernet0/0/0
    O       10.2.0.0/16 [110/2] via 10.0.0.49, 00:13:11, GigabitEthernet0/0/0
         192.168.10.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.10.0/24 is directly connected, GigabitEthernet0/0/1.10
    L       192.168.10.1/32 is directly connected, GigabitEthernet0/0/1.10
         192.168.20.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.20.0/24 is directly connected, GigabitEthernet0/0/1.20
    L       192.168.20.1/32 is directly connected, GigabitEthernet0/0/1.20
         192.168.30.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.30.0/24 is directly connected, GigabitEthernet0/0/1.30
    L       192.168.30.1/32 is directly connected, GigabitEthernet0/0/1.30
         192.168.50.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.50.0/24 is directly connected, GigabitEthernet0/0/1.50
    L       192.168.50.1/32 is directly connected, GigabitEthernet0/0/1.50
         192.168.75.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.75.0/24 is directly connected, GigabitEthernet0/0/1.75
    L       192.168.75.1/32 is directly connected, GigabitEthernet0/0/1.75
         192.168.99.0/24 is variably subnetted, 2 subnets, 2 masks
    C       192.168.99.0/24 is directly connected, GigabitEthernet0/0/1.99
    L       192.168.99.1/32 is directly connected, GigabitEthernet0/0/1.99
    S*   0.0.0.0/0 is directly connected, GigabitEthernet0/0/0
    
    HQ-Edge# 

1-c-a) ¿Cuál es la dirección de la puerta de enlace de último recurso (o puerta de enlace predeterminada)?

    S*   0.0.0.0/0 is directly connected, GigabitEthernet0/0/0

1-c-b) ¿Por qué no se muestra la dirección del siguiente salto?
No está configurado

1-d) Ingresé el comando running-config | begin ip route.

    HQ-Edge# running-config | begin ip
                            ^
    % Invalid input detected at '^' marker.
        
    HQ-Edge#  show running-config | begin ip route
    ip route 0.0.0.0 0.0.0.0 GigabitEthernet0/0/0 
    !
    ip flow-export version 9
    !
    !
    ip access-list standard NAT-PERMIT
     permit 192.168.10.0 0.0.0.255
     permit 192.168.20.0 0.0.0.255
     permit 192.168.99.0 0.0.0.15
     permit 192.168.75.0 0.0.0.7
    ip access-list standard ADMIN-ONLY
     permit 192.168.99.0 0.0.0.255
     deny any
    access-list 101 permit ip 192.168.10.0 0.0.0.255 10.0.3.0 0.0.0.255
    access-list 101 permit ip 192.168.20.0 0.0.0.255 10.0.3.0 0.0.0.255
    access-list 101 permit ip 192.168.75.0 0.0.0.255 10.0.3.0 0.0.0.255
    access-list 101 permit ip 192.168.99.0 0.0.0.255 10.0.3.0 0.0.0.255
    access-list 101 permit icmp any 10.0.3.0 0.0.0.255
    ip access-list extended NAT-NOVPN
     permit ip 192.168.0.0 0.0.255.255 10.2.0.0 0.0.255.255
     permit ip 192.168.0.0 0.0.255.255 10.1.0.0 0.0.255.255
     permit ip 192.168.0.0 0.0.255.255 192.168.0.0 0.0.0.255
     permit ip 192.168.0.0 0.0.255.255 172.0.0.0 0.0.255.255
    !
    !
    !
    !
    !
    !
    line con 0
    !
    line aux 0
    !
    line vty 0 4
     login
    !
    !
    !
    end
    
    
    HQ-Edge#


¿Cómo se configura la ruta por defecto? ¿Utiliza la dirección del siguiente salto?
Está configurado con la interfaz de salida en lugar de la dirección del siguiente salto.

1-e) Ingresé el comando show cdp neighbours detail.

    HQ-Edge#  show cdp neighbors detail
    
    Device ID: ISP
    Entry address(es): 
      IP address : 10.0.0.49
    Platform: cisco PT1000, Capabilities: Router
    Interface: GigabitEthernet0/0/0, Port ID (outgoing port): GigabitEthernet1/0
    Holdtime: 121
    
    Version :
    Cisco Internetwork Operating System Software
    IOS (tm) PT1000 Software (PT1000-I-M), Version 12.2(28), RELEASE SOFTWARE (fc5)
    Technical Support: http://www.cisco.com/techsupport
    Copyright (c) 1986-2005 by cisco Systems, Inc.
    Compiled Wed 27-Apr-04 19:01 by miwang
    
    advertisement version: 2
    Duplex: full
    
    HQ-Edge#

¿Cuál es la dirección IPv4 de la dirección del siguiente salto (ISP)?

    IP address : 10.0.0.49

¿Qué puerto del enrutador ISP está conectado a HQ-Edge?

    Interface: GigabitEthernet0/0/0

¿Qué versión de IOS se usa en el enrutador ISP?

    IOS (tm) PT1000 Software (PT1000-I-M), Version 12.2(28) RELEASE SOFTWARE (fc5)

1-f) Ingrese el comando ping 10.0.0.49.

    HQ-Edge# ping 10.0.0.49
    
    Type escape sequence to abort.
    Sending 5, 100-byte ICMP Echos to 10.0.0.49, timeout is 2 seconds:
    !!!!!
    Success rate is 100 percent (5/5), round-trip min/avg/max = 0/0/0 ms
    
    HQ-Edge#

1-g) Ingresé el comando show arp

    HQ-Edge# show arp
    Protocol  Address          Age (min)  Hardware Addr   Type   Interface
    Internet  10.0.0.49               42  0060.2FE1.903B  ARPA   GigabitEthernet0/0/0
    Internet  10.0.0.50               -   0000.0C99.CB04  ARPA   GigabitEthernet0/0/0
    Internet  192.168.99.10           42  0090.2B03.46D1  ARPA   GigabitEthernet0/0/1.99
    HQ-Edge#

¿Cuál es la dirección MAC de la interfaz en el enrutador ISP que está conectado a HQ-Edge?

    0060.2FE1.903B


2-a) Desde 1-1, 1-2, 1-3, 1-4, FL-1P y HQ-Laptop-1, usé el comando ipconfig para encontrar sus direcciones IPv4 y 
puertas de enlace predeterminadas


pc 1-1

    C:\>ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::201:C7FF:FE54:EB5
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.10.4
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.10.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0

-------------------------------------------------
pc 1-2

    C:\>ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::202:4AFF:FE8A:D20E
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.10.3
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.10.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0

-------------------------------------------------
pc 1-3

    C:\>ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::201:C9FF:FEE9:887E
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.20.3
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.20.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0

----------------------------------------------------
pc 1-4

    C:\>ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::201:97FF:FEBA:7BB0
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.20.4
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.20.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0

--------------------------------------------------------
FL-1P

    IPV4 Address 192.168.50.4
    Defeault Gateway 192.168.50.1

-------------------------------------------------------

HQ-Laptop-1

    C:\>ipconfig
    
    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::20A:F3FF:FEE4:EEAA
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.50.2
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.50.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0


Completé la tabla:

    Device      |   IPv4 Address    |    Default Gateway

    1-1         |   192.168.10.4    |    192.168.10.1
    1-2         |   192.168.10.3    |    192.168.10.1
    1-3         |   192.168.20.3    |    192.168.20.1
    1-4         |   192.168.20.4    |    192.168.20.1
    FL-1P       |   192.168.50.4    |    192.168.50.1
    HQ-Laptop-1 |   192.168.50.2    |    192.168.50.1


2-b) Desde la PC 1-1, abrí el Símbolo del sistema y luego ingrese el comando arp -a.

    C:\>arp -a
    No ARP Entries Found

¿Qué información se muestra?
NO se encuentraron entradas ARP

2-c) Use el comando ping para verificar la conectividad con las pcs: 1-2, 1-3, 1-4, la impresora
FL-1P y la laptop HQ-Laptop-1

    C:\> ping 192.168.10.3
    
    Pinging 192.168.10.3 with 32 bytes of data:
    
    Reply from 192.168.10.3: bytes=32 time<1ms TTL=128
    Reply from 192.168.10.3: bytes=32 time<1ms TTL=128
    Reply from 192.168.10.3: bytes=32 time<1ms TTL=128
    Reply from 192.168.10.3: bytes=32 time<1ms TTL=128
    
    Ping statistics for 192.168.10.3:
        Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 0ms, Maximum = 0ms, Average = 0ms
    
    C:\>ping 192.168.20.3
    
    Pinging 192.168.20.3 with 32 bytes of data:
    
    Request timed out.
    Reply from 192.168.20.3: bytes=32 time<1ms TTL=127
    Reply from 192.168.20.3: bytes=32 time<1ms TTL=127
    Reply from 192.168.20.3: bytes=32 time<1ms TTL=127
    
    Ping statistics for 192.168.20.3:
        Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 0ms, Maximum = 0ms, Average = 0ms
    
    C:\> ping 192.168.20.4
    
    Pinging 192.168.20.4 with 32 bytes of data:
    
    Request timed out.
    Reply from 192.168.20.4: bytes=32 time<1ms TTL=127
    Reply from 192.168.20.4: bytes=32 time=2ms TTL=127
    Reply from 192.168.20.4: bytes=32 time<1ms TTL=127
    
    Ping statistics for 192.168.20.4:
        Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 0ms, Maximum = 2ms, Average = 0ms
    
    C:\>ping 192.168.50.4
    
    Pinging 192.168.50.4 with 32 bytes of data:
    
    Request timed out.
    Reply from 192.168.50.4: bytes=32 time=15ms TTL=127
    Reply from 192.168.50.4: bytes=32 time=10ms TTL=127
    Reply from 192.168.50.4: bytes=32 time=41ms TTL=127
    
    Ping statistics for 192.168.50.4:
        Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 10ms, Maximum = 41ms, Average = 22ms
    
    C:\> ping 192.168.50.2
    
    Pinging 192.168.50.2 with 32 bytes of data:
    
    Request timed out.
    Reply from 192.168.50.2: bytes=32 time=22ms TTL=127
    Reply from 192.168.50.2: bytes=32 time=2ms TTL=127
    Reply from 192.168.50.2: bytes=32 time=30ms TTL=127
    
    Ping statistics for 192.168.50.2:
        Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 2ms, Maximum = 30ms, Average = 18ms

2-d) Ingresé el comando arp -a.

    C:\>arp -a
      Internet Address      Physical Address      Type
      192.168.10.1          000a.41ea.6b47        dynamic
      192.168.10.3          0002.4a8a.d20e        dynamic

¿Qué información se muestra?

la direccion IP, la direccion MAC y el tipo de conexion (dinamica)

¿Por qué las entradas en la tabla ARP no contienen información sobre los dispositivos en las redes 192.168.20.0 y 
192.168.50.0 mientras el ping es exitoso?
192.168.10.0/24, 192.168.20.0/24 y 192.168.50.0/24 están en diferentes VLAN. Hacer ping desde la red 192.168.10.0 a 
otras redes VLAN primero debería pasar por la puerta de enlace predeterminada. Por lo tanto, la tabla ARP solo contiene 
la información sobre los dispositivos dentro de la misma red o la misma VLAN.

2-e) Para encontrar la ruta que toma un paquete para llegar al servidor DNS, ingresé el comando tracert 10.2.0.125.
¿Qué información se muestra?

    C:\>tracert 10.2.0.125
    
    Tracing route to 10.2.0.125 over a maximum of 30 hops: 
    
      1   0 ms      0 ms      0 ms      192.168.10.1
      2   0 ms      0 ms      0 ms      10.0.0.49
      3   0 ms      0 ms      0 ms      10.2.0.125
    
    Trace complete.
    
    C:\>

¿Cuántos enrutadores o saltos hay entre la PC 1-1 y el servidor DNS?
Hay 2 saltos


## Parte 3: Diagnosticar problemas de conectividad

1-b) Introducí la URL test.ptsecurity.com ¿Se muestra la página web? Si no, ¿cuál es el mensaje? 
NO muestra la pagina web, el mensaje de error es "Host Name Unresolved"

1-c) Ingresé la dirección IP 192.168.75.2. ¿Se muestra la página web?
¿Por qué la página web se muestra usando la dirección IP pero no el nombre de dominio?
Si muestra la pagina web. La PC no puede resolver el nombre de dominio a la dirección IP.

2-b) Ingresé el comando ping test.ptsecurity.com. ¿Qué mensaje se muestra?

    C:\>ping test.ptsecurity.com
    Ping request could not find host test.ptsecurity.com. Please check the name and try again.
    C:\>

¿Qué indica el mensaje?
Por favor revisar el nombre y prueba de nuevo.

2-c) Ingrese el comando nslookup test.ptsecurity.com. ¿Qué mensaje se muestra?

    C:\> nslookup test.ptsecurity.com 
    
    Server: [10.2.0.125]
    Address:  10.2.0.125
    *** UnKnown can't find test.ptsecurity.com: Non-existent domain.

¿Qué servidor es el servidor DNS predeterminado?
    
    Server: [10.2.0.125]

2-d) El comando nslookup admite el uso de un servidor DNS alternativo. Introduzca el comando nslookup /? 
para conocer las opciones disponibles para el comando.

    C:\>  nslookup /?
    Usage:
    
    nslookup              # interactive mode using default server
    nslookup host         # just look up 'host' using default server
    nslookup host a.b.c.d # just look up 'host' using DNS server with ip address 'a.b.c.d'
    C:\>

2-e) Ingresé el comando nslookup test.ptsecurity.com 192.168.99.3 ¿Qué mensaje se muestra?

    C:\>nslookup test.ptsecurity.com 192.168.99.3
    
    Server: [192.168.99.3]
    Address:  192.168.99.3
    DNS request timed out.
        timeout was 15000 milli seconds.
    
    Server: [192.168.99.3]
    Address:  192.168.99.3
    
    Non-authoritative answer:
    Name:   test.ptsecurity.com
    Address:   192.168.75.2

En el paso 2c, ¿por qué no se puede resolver el nombre de dominio?
Cuando se ingresa un nombre de dominio en el cuadro URL, la PC intenta resolverlo a través del servidor DNS 
predeterminado. En este caso, el servidor DNS predeterminado no contiene la información en su base de datos.

3-a) Ingresé el comando ping mail.cybercloud.com. Que mensaje se muestra?

    C:\> ping mail.cybercloud.com
    
    Pinging 172.19.0.4 with 32 bytes of data:
    
    Request timed out.
    Request timed out.
    Request timed out.
    Request timed out.
    
    Ping statistics for 172.19.0.4:
        Packets: Sent = 4, Received = 0, Lost = 4 (100% loss),

¿Qué información indica el mensaje?
La resolución de nombres DNS es exitosa. Sin embargo, el ping falló. Los posibles motivos son que el host está inactivo 
o que el eco/respuesta de eco ICMP está deshabilitado en el host.

3-b) Ingresé el comando ping www.ptsecurity.com. ¿Qué mensaje se muestra?

    C:\> ping www.ptsecurity.com
    
    Pinging 10.0.0.3 with 32 bytes of data:
    
    Request timed out.
    Request timed out.
    Reply from 10.0.0.3: Destination host unreachable.
    Reply from 10.0.0.3: Destination host unreachable.
    
    Ping statistics for 10.0.0.3:
        Packets: Sent = 4, Received = 0, Lost = 4 (100% loss),

Qué información indica el mensaje?
Hay un firewall en la ruta que bloquea el ping al destino.

3-c) Desde el navegador web fui a www.ptsecurity.com. ¿Se muestra la página web?
Si se muestra la pagina

¿Qué conclusión se puede sacar?
El servidor web se está ejecutando; sin embargo, el ping al servidor web está bloqueado.

4-e) Desde la PC 1-1, ingresé el comando netstat.¿Qué mensaje se muestra? ¿Muestra algún dato?

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State

NO muestra ningun dato

4-f) Desde el servidor FTP, ingresé el comando netstat.¿Qué mensaje se muestra? ¿Muestra algún dato?

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
    C:\>

No muestra ninguna conexión activa con otros dispositivos ni puertos de escucha.

4-g) En el servidor FTP, ingresé el comando ipconfig para determinar su dirección IP.

    C:\> ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::290:21FF:FE64:E9B9
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.75.2
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.75.1

4-h) Desde la PC 1-1, inicie una sesión FTP con el servidor FTP. 

    C:\>ftp 192.168.75.2
    Trying to connect...192.168.75.2
    Connected to 192.168.75.2
    220- Welcome to PT Ftp server
    Username:

4-i) En el servidor FTP, ingrese el comando netstat.

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
      TCP    192.168.75.2:21        192.168.10.4:1027      ESTABLISHED
    C:\>

¿Qué mensaje se muestra? ¿Hay alguna información nueva?
Sí, una nueva entrada muestra:

    TCP    192.168.75.2:21        192.168.10.4:1027      ESTABLISHED

¿Qué puerto es el puerto de escucha y cuál es el estado de la conexión?
Puerto de escucha: 21 y la conexion TCP esta establecida

4-j) Desde PC 1-1, ingrese bob como nombre de usuario.

    C:\>ftp 192.168.75.2
    Trying to connect...192.168.75.2
    Connected to 192.168.75.2
    220- Welcome to PT Ftp server
    Username:bob
    331- Username ok, need password
    Password:

4-k) Desde el servidor FTP, ingrese el comando netstat.

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
      TCP    192.168.75.2:21        192.168.10.4:1027      ESTABLISHED
    C:\>

¿Cambia la información mostrada?
NO

4-l) Desde la PC 1-1, ingrese cisco123 como contraseña.

    C:\>ftp 192.168.75.2
    Trying to connect...192.168.75.2
    Connected to 192.168.75.2
    220- Welcome to PT Ftp server
    Username:bob
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>

4-m) Desde la PC 1-1, ingrese el comando dir.

    ftp>dir
    
    Listing /ftp directory from 192.168.75.2: 
    ftp>

4-n) Desde el servidor FTP, ingrese el comando netstat.

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
      TCP    192.168.75.2:21        192.168.10.4:1028      ESTABLISHED
      TCP    192.168.75.2:1028      192.168.10.4:1029      CLOSED
    C:\>

¿Cambia la información mostrada?
Si. Una nueva entrada muestra:

    TCP    192.168.75.2:1028      192.168.10.4:1029      CLOSED

4-o) Desde la PC 1-1, ingresé el comando put Sample2.txt para cargar el archivo Sample2.txt al servidor FTP.

    ftp>put Sample2.txt
    
    Writing file Sample2.txt to 192.168.75.2: 
    File transfer in progress...
    
    [Transfer complete - 43 bytes]
    
    43 bytes copied in 0.079 secs (544 bytes/sec)
    ftp>

4-p) Desde el servidor FTP, ingresé el comando netstat.

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
      TCP    192.168.75.2:21        192.168.10.4:1028      ESTABLISHED
    C:\>

¿Cambia la información mostrada?
Si. La línea "CLOSED" se ha ido.

4-q) Esperé unos segundos y luego ingrese el comando netstat nuevamente.
¿Cambia la información mostrada?
NO

4-r) Desde PC 1-1, ingresé el comando quit para salir del servidor

    ftp>quit
    
    221- Service closing control connection.
    C:\>

4-s) Desde el servidor FTP, ingresé el comando netstat. ¿Cambia la información mostrada?

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
    C:\>

Si, ahora la conexión TCP entre 192.168.75.2:21 y 192.168.10.4:1028 está CERRADA.

4-v) Desde el servidor FTP, ingrese el comando netstat. 

    C:\>netstat
    
    Active Connections
    
      Proto  Local Address          Foreign Address        State
      TCP    0.0.0.0:25             0.0.0.0:0              CLOSED
      TCP    0.0.0.0:110            0.0.0.0:0              CLOSED
      TCP    0.0.0.0:8443           0.0.0.0:0              CLOSED
      TCP    192.168.75.2:80        192.168.10.4:1031      CLOSED
    C:\>

¿Cambia la información mostrada?
Si, hay una nueva entrada:
    
    TCP    192.168.75.2:80        192.168.10.4:1031      CLOSED

¿Qué indica esta nueva entrada?
El host 192.168.10.2 realiza una solicitud de página web. La página web se transmite (se muestra en el navegador web de 
la PC 1-1) y la conexión TCP se cierra.