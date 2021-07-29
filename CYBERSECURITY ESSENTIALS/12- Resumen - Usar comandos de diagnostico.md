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


