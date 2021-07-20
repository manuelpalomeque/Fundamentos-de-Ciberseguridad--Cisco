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

