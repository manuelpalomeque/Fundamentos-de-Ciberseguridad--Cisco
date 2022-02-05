## Parte 1: configurar una red inalámbrica doméstica

### Paso 1: Configure la red inalámbrica doméstica.

a) Determine la direcion IP actual del router desde Home Office PC:

    C:\>ipconfig
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: FE80::2E0:A3FF:FE4E:262B
       IPv6 Address....................: ::
       IPv4 Address....................: 192.168.0.4
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         192.168.0.1
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       Autoconfiguration IPv4 Address..: 169.254.38.43
       Subnet Mask.....................: 255.255.0.0
       Default Gateway.................: ::
                                         0.0.0.0


Direccion IP del Router: 192.168.0.1

b) configure el HOme Wireles Router usando "admin" como usuario y clave

3) Verifique que todos los dispositivos cableados e inalámbricos tengan direccionamiento IP.

Home Office PC

    C:\>ipconfig /all
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 00E0.A34E.262B
       Link-local IPv6 Address.........: FE80::2E0:A3FF:FE4E:262B
       IPv6 Address....................: ::
       IPv4 Address....................: 172.16.10.227
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         172.16.10.1
       DHCP Servers....................: 172.16.10.1
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-15-BE-64-EC-00-E0-A3-4E-26-2B
       DNS Servers.....................: ::
                                         10.2.0.125
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 0001.973B.D767
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       Autoconfiguration IP Address....: 169.254.38.43
       Subnet Mask.....................: 255.255.0.0
       Default Gateway.................: ::
                                         0.0.0.0
       DHCP Servers....................: 0.0.0.0
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-15-BE-64-EC-00-E0-A3-4E-26-2B
       DNS Servers.....................: ::
                                         10.2.0.125
    
    ---------------------------------------------------------------------------------------------
Jose Laptop
    
    C:\>ipconfig /all
    
    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 0001.9636.CE4C
       Link-local IPv6 Address.........: FE80::201:96FF:FE36:CE4C
       IPv6 Address....................: ::
       IPv4 Address....................: 172.16.10.231
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         172.16.10.1
       DHCP Servers....................: 172.16.10.1
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-EA-E8-62-64-00-01-96-36-CE-4C
       DNS Servers.....................: ::
                                         10.2.0.125
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 0002.1791.C155
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0
       DHCP Servers....................: 0.0.0.0
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-EA-E8-62-64-00-01-96-36-CE-4C
       DNS Servers.....................: ::
                                         10.2.0.125
    
    --------------------------------------------------------------------------------------------
Home_Webcam
    
    Default Gateway : 172.16.10.1
    DNS Server: 10.2.0.125
    
    ---------------------------------------------------------------------------------------------
Family PC
    
    C:\>ipconfig /all
    
    FastEthernet0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 0001.97DB.C011
       Link-local IPv6 Address.........: FE80::201:97FF:FEDB:C011
       IPv6 Address....................: ::
       IPv4 Address....................: 172.16.10.226
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         172.16.10.1
       DHCP Servers....................: 172.16.10.1
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-2B-34-59-CE-00-01-97-DB-C0-11
       DNS Servers.....................: ::
                                         10.2.0.125
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 0060.47A9.656A
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0
       DHCP Servers....................: 0.0.0.0
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-2B-34-59-CE-00-01-97-DB-C0-11
       DNS Servers.....................: ::
                                         10.2.0.125
    -----------------------------------------------------------------------------------------
Guest Laptop
    
    C:\>ipconfig /all
    
    Wireless0 Connection:(default port)
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 00E0.F76E.B5CA
       Link-local IPv6 Address.........: FE80::2E0:F7FF:FE6E:B5CA
       IPv6 Address....................: ::
       IPv4 Address....................: 172.16.10.232
       Subnet Mask.....................: 255.255.255.0
       Default Gateway.................: ::
                                         172.16.10.1
       DHCP Servers....................: 172.16.10.1
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-C0-70-B9-09-00-E0-F7-6E-B5-CA
       DNS Servers.....................: ::
                                         10.2.0.125
    
    Bluetooth Connection:
    
       Connection-specific DNS Suffix..: 
       Physical Address................: 00E0.B035.2D57
       Link-local IPv6 Address.........: ::
       IPv6 Address....................: ::
       IPv4 Address....................: 0.0.0.0
       Subnet Mask.....................: 0.0.0.0
       Default Gateway.................: ::
                                         0.0.0.0
       DHCP Servers....................: 0.0.0.0
       DHCPv6 IAID.....................: 
       DHCPv6 Client DUID..............: 00-01-00-01-C0-70-B9-09-00-E0-F7-6E-B5-CA
       DNS Servers.....................: ::
                                         10.2.0.125
    
    -------------------------------------------------------------------------------------------
Home_Siren
    
    Default Gateway : 172.16.10.1
    DNS Server: 10.2.0.125
    
    -------------------------------------------------------------------------------------------
Home Doors
    
    Default Gateway : 172.16.10.1
    DNS Server: 10.2.0.125


### Paso 4: Registre los dispositivos IoT domésticos en el servidor de registro de IoT

    direccion: 10.3.0.125
    usuario: admin
    clave: admin


