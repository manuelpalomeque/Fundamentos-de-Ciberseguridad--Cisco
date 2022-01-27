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

