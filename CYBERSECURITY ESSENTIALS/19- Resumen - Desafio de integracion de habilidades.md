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

## Parte 2: configurar y usar una VPN de acceso remoto

### Paso 4: Cargue un archivo en el sitio FTP de DC.

usuario: jose
clave: josepass


    C:\>ftp 172.19.0.3
    Trying to connect...172.19.0.3
    Connected to 172.19.0.3
    220- Welcome to PT Ftp server
    Username:jose
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>dir
    
    Listing /ftp directory from 172.19.0.3: 
    0   : PTsecurity.txt                                     92
    ftp>put Instructions.txt
    
    Writing file Instructions.txt to 172.19.0.3: 
    File transfer in progress...
    
    [Transfer complete - 1303 bytes]
    
    1303 bytes copied in 0.041 secs (31780 bytes/sec)
    ftp>dir
    
    Listing /ftp directory from 172.19.0.3: 
    0   : Instructions.txt                                   1303
    1   : PTsecurity.txt                                     92
    ftp>quit
    
    221- Service closing control connection.
    C:\>

### Paso 5: Enviar un correo electrónico a Mariel sobre la carga del archivo.

a) 

    Hi Mariel,
    I have uploaded the file Instructions.txt to the DC_FTP Server (172.19.0.3). The MD5sum hash for the file is 0b9b2d509aab15df7e7eb2eca105b3a9
    
    In a terminal window in the VM, enter the following command, pasting the contents of your clipboard in place of 'file-contents', to verify the files integrity:
    echo -n 'file-contents' | md5sum
    
    The hash (Instructions_Hash.html) is also stored at www.ptsecurity.com for public use.
    Thanks,
    Jose

### Paso 6: Verifique la integridad del archivo cargado en el servidor FTP.

username: mariel
clave: marielpass

    C:\>ftp 172.19.0.3
    Trying to connect...172.19.0.3
    Connected to 172.19.0.3
    220- Welcome to PT Ftp server
    Username:mariel
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>dir
    
    Listing /ftp directory from 172.19.0.3: 
    0   : Instructions.txt                                   1303
    1   : PTsecurity.txt                                     92
    ftp>get Instructions.txt
    
    Reading file Instructions.txt from 172.19.0.3: 
    File transfer in progress...
    
    [Transfer complete - 1303 bytes]
    
    1303 bytes copied in 0.156 secs (8352 bytes/sec)
    ftp>quit
    
    221- Service closing control connection.
    C:\>


c) 

    Video provides a powerful way to help you prove your point. When you click Online Video, you can paste in the embed 
    code for the video you want to add. You can also type a keyword to search online for the video that best fits your 
    document. To make your document look professionally produced, Word provides header, footer, cover page, and text 
    box designs that complement each other. For example, you can add a matching cover page, header, and sidebar. 
    Click Insert and then choose the elements you want from the different galleries. Themes and styles also help keep 
    your document coordinated. When you click Design and choose a new Theme, the pictures, charts, and SmartArt 
    graphics change to match your new theme. When you apply styles, your headings change to match the new theme. Save 
    time in Word with new buttons that show up where you need them. 
    To change the way a picture fits in your document, click it and a button for layout options appears next to it. 
    When you work on a table, click where you want to add a row or a column, and then click the plus sign. Reading is 
    easier, too, in the new Reading view. You can collapse parts of the document and focus on the text you want. If you 
    need to stop reading before you reach the end, Word remembers where you left off - even on another device.


    cisco@labvm:~$ echo -n 'Video provides a powerful way to help you prove your point. When you click Online Video, you 
    can paste in the embed code for the video you want to add. You can also type a keyword to search online for the video 
    that best fits your document. To make your document look professionally produced, Word provides header, footer, cover 
    page, and text box designs that complement each other. For example, you can add a matching cover page, header, and 
    sidebar. Click Insert and then choose the elements you want from the different galleries. Themes and styles also help 
    keep your document coordinated. When you click Design and choose a new Theme, the pictures, charts, and SmartArt 
    graphics change to match your new theme. When you apply styles, your headings change to match the new theme. Save time 
    in Word with new buttons that show up where you need them. To change the way a picture fits in your document, click it 
    and a button for layout options appears next to it. When you work on a table, click where you want to add a row or a 
    column, and then click the plus sign. Reading is easier, too, in the new Reading view. You can collapse parts of the 
    document and focus on the text you want. If you need to stop reading before you reach the end, Word remembers where 
    you left off - even on another device. ' | md5sum
    90594bd36d1059a1a19f723441b3a86e  -

## Parte 3: configurar y usar una VPN de sitio a sitio


### Paso 3: Restaure y verifique la VPN de sitio a sitio.

b)

    %DHCPD-4-PING_CONFLICT: DHCP address conflict:  server pinged 10.0.3.102.
    Authorized Access Only!
    
    User Access Verification
    
    Password: 
    
    Branch>enable
    Password: 
    Branch# copy tftp running-config
    Address or name of remote host []? 10.0.3.30
    Source filename []? Branch-config
    Destination filename [running-config]? 
    
    Accessing tftp://10.0.3.30/Branch-config....
    Loading Branch-config from 10.0.3.30: !
    [OK - 2546 bytes]
    
    2546 bytes copied in 3.004 secs (847 bytes/sec)
    Branch#
    %SYS-5-CONFIG_I: Configured from console by console

c)

    Branch#config t
    Enter configuration commands, one per line.  End with CNTL/Z.
    Branch(config)#no access-list 102
    Branch(config)#access-list 102 permit ip 10.0.3.0 0.0.0.255 10.1.0.0 0.0.255.255
    Branch(config)#access-list 102 permit ip 10.0.3.0 0.0.0.255 10.2.0.0 0.0.255.255
    Branch(config)#access-list 102 permit ip 10.0.3.0 0.0.0.255 10.3.0.0 0.0.255.255
    Branch(config)#
