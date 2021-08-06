## Parte 2: Exploré el analizador de protocolos Wireshark.

a) Tuve que ejecutar Wireshark en modo promiscuo, lo que requiere ejecutar con privilegios escalados, mediante sudo. 
Ingresé el comando sudo wireshark y luego ingrese la contraseña que es password. Se abrió la interfaz gráfica de usuario 
(GUI) de Wireshark.

    cisco@labvm:~$ sudo wireshark
    [sudo] password for cisco: 
    QStandardPaths: XDG_RUNTIME_DIR not set, defaulting to '/tmp/runtime-root'

b) En la lista de interfaces, seleccioné "any" y luego hice clic en Capture > Start en los menús. Tambien,
puedo hacer clic en el icono de la aleta de tiburón. Wireshark comenzará a capturar paquetes

c) Abri Firefox, continúe y Wireshark, ahora muestra el tráfico TCP capturado en el tercio superior de la 
ventana

    No.	Time	Source	Destination	Protocol	Length	Info
    84	0.230596184	10.0.2.15	34.107.221.82	TCP	56	44034 → 80 [ACK] Seq=1 Ack=1 Win=64240 Len=0
    86	0.230799635	34.107.221.82	10.0.2.15	TCP	62	80 → 44034 [ACK] Seq=1 Ack=302 Win=65535 Len=0
    92	0.252258278	10.0.2.15	34.107.221.82	TCP	56	44034 → 80 [ACK] Seq=302 Ack=221 Win=64020 Len=0
    83	0.230569093	34.107.221.82	10.0.2.15	TCP	62	80 → 44034 [SYN, ACK] Seq=0 Ack=1 Win=65535 Len=0 MSS=1460
    62	0.206732361	10.0.2.15	34.107.221.82	TCP	76	44034 → 80 [SYN] Seq=0 Win=64240 Len=0 MSS=1460 SACK_PERM=1 TSval=295661337 TSecr=0 WS=128

d) En Firefox, ingresé a www.cisco.com para visitar el sitio web de Cisco. Después de que se cargue el sitio web, 
cerré Firefox.

e) Luego en Wireshark y haga clic en Capture > Stop en los menús. Alternativamente.

f) En Wireshark, verá el campo de filtro y tres paneles clave o áreas de trabajo:

-> El campo Aplicar un filtro de visualización está directamente debajo de la barra de herramientas.

-> El panel Lista de paquetes incluye las siguientes columnas para cada paquete capturado:
    * No: el número del paquete (en orden numérico).
    * Time: la marca de tiempo del paquete
    * Source: la dirección IP de origen del paquete
    * Destination: la dirección IP de destino del paquete
    * Protocol: el protocolo del paquete
    * Length: la cantidad de bytes capturados para este paquete
    * Info: información adicional sobre el contenido del paquete

-> El Packet Details (panel Detalles) del paquete muestra los protocolos y los campos de protocolo del paquete seleccionado. Darse cuenta de
los campos se pueden expandir o contraer haciendo clic en la flecha al lado del campo.

-> El Packet Bytes (panel Bytes) del paquete muestra los detalles de los bytes del paquete seleccionado. A medida que selecciona partes 
del paquete en el panel Detalles del paquete, los bytes correspondientes se resaltarán en los Bytes del paquete
cristal. El lado izquierdo muestra la representación hexadecimal de los bytes, y el lado derecho muestra la
Representación ASCII

## Parte 3: Capture y analice el tráfico Telnet sin cifrar:

a) Iniciar una nueva captura. En el cuadro de diálogo Paquetes no guardados (Unsaved packets)... haga clic en Continuar
sin guardar. Esto borrará los paquetes de su última captura y comenzará una nueva captura.

C) Abri una nueva terminal. Puede simular un inicio de sesión remoto en su máquina virtual ingresando el comando "telnet
localhost" y luego iniciando sesión como "cisco" con "password" como contraseña.

    cisco@labvm:~$ telnet localhost
    Trying ::1...
    Trying 127.0.0.1...
    Connected to localhost.
    Escape character is '^]'.
    Ubuntu 20.04.3 LTS
    labvm login: cisco
    Password: 
    Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-96-generic x86_64)

        * Documentation:  https://help.ubuntu.com
        * Management:     https://landscape.canonical.com
        * Support:        https://ubuntu.com/advantage

      0 updates can be applied immediately.


    The list of available updates is more than a week old.
    To check for new updates run: sudo apt update
    Last login: Thu Mar 18 21:47:23 UTC 2021 on tty2
    cisco@labvm:~$ 

d) Ingrese el comando "exit" para finalizar la sesión de Telnet:

    cisco@labvm:~$ exit
    logout
    Connection closed by foreign host.
    cisco@labvm:~$ 

e) Regrese a Wireshark y detenga la captura, haciendo click en stop.

f) En el campo Aplicar un filtro de visualización, escriba telnet y presione Entrar para filtrar solo los paquetes 
Telnet

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/img.png">

    No.	Time	Source	Destination	Protocol	Length	Info
    6	0.000087243	127.0.0.1	127.0.0.1	TELNET	95	Telnet Data ...
    8	0.005783648	127.0.0.1	127.0.0.1	TELNET	80	Telnet Data ...
    10	0.005809516	127.0.0.1	127.0.0.1	TELNET	107	Telnet Data ...
    12	0.005847733	127.0.0.1	127.0.0.1	TELNET	155	Telnet Data ...
    14	0.005944584	127.0.0.1	127.0.0.1	TELNET	71	Telnet Data ...
    16	0.005955715	127.0.0.1	127.0.0.1	TELNET	71	Telnet Data ...
    18	0.006812089	127.0.0.1	127.0.0.1	TELNET	71	Telnet Data ...
    20	0.006823911	127.0.0.1	127.0.0.1	TELNET	88	Telnet Data ...
    22	0.006859959	127.0.0.1	127.0.0.1	TELNET	71	Telnet Data ...
    24	0.013151578	127.0.0.1	127.0.0.1	TELNET	81	Telnet Data ...
    26	26.662884293	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    28	26.662992842	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    30	26.846944348	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    32	26.847029287	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    34	26.971851060	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    36	26.971935092	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    38	27.193058759	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    39	27.193137020	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    41	27.314935350	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    42	27.315006118	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    44	27.690043067	127.0.0.1	127.0.0.1	TELNET	70	Telnet Data ...
    45	27.690113514	127.0.0.1	127.0.0.1	TELNET	70	Telnet Data ...
    47	27.690470613	127.0.0.1	127.0.0.1	TELNET	78	Telnet Data ...
    49	28.692129714	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    51	28.795967814	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    53	29.057961853	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    55	29.230039874	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    57	29.453842318	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    59	29.635811997	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    61	29.834855471	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    63	30.074987577	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    65	30.286908802	127.0.0.1	127.0.0.1	TELNET	70	Telnet Data ...
    67	30.289917898	127.0.0.1	127.0.0.1	TELNET	70	Telnet Data ...
    69	30.509649607	127.0.0.1	127.0.0.1	TELNET	430	Telnet Data ...
    71	30.510485463	127.0.0.1	127.0.0.1	TELNET	118	Telnet Data ...
    73	30.563276533	127.0.0.1	127.0.0.1	TELNET	128	Telnet Data ...
    116	571.937864676	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    118	571.937963296	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    120	572.173857473	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    122	572.173962851	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    124	572.380711332	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    125	572.380804631	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    127	572.544765885	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    128	572.544856970	127.0.0.1	127.0.0.1	TELNET	69	Telnet Data ...
    130	572.678618503	127.0.0.1	127.0.0.1	TELNET	70	Telnet Data ...
    131	572.678957989	127.0.0.1	127.0.0.1	TELNET	78	Telnet Data ...

g) En la barra de herramientas, haga clic en el icono de la lupa para encontrar un paquete. Ahora se muestran funciones 
de búsqueda adicionales debajo del campo Aplicar un filtro de visualización.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/img_1.png">

h) Haga clic en las flechas junto a Mostrar filtro (Display filter) y cámbielo a Cadena (String). Luego haga clic en las flechas al lado de 
Lista de paquetes y cámbielo a Detalles del paquete.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/img_3.png">

i) Para encontrar el paquete que solicita la información de inicio de sesión, escriba "labvm login", en el campo junto a 
Cadena y luego presione Entrar o haga clic en Buscar. Wireshark resaltará el paquete que contiene la cadena de texto "labvm login:".

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/img_4.png">

j) En el panel Detalles del paquete, haga clic en la flecha junto a Telnet para expandir su contenido. Debería ver que 
labvm login: son los datos para este paquete. Los datos del paquete también se muestran en el panel Bytes del paquete. 
Puede decir que el texto se envió sin cifrar porque puede leerlo.

    Telnet:
        Data: labvm login: 

l) Para encontrar el nombre de usuario y la contraseña, use la flecha hacia abajo en el teclado para seleccionar el 
siguiente paquete. En el panel Detalles del paquete, debería ver que el valor de Datos en Telnet es la primera letra 
que escribió en el campo para el indicador "labvm login:", que era c para cisco. Si vuelve a hacer clic en la flecha 
hacia abajo, verá los datos del siguiente paquete también son c. Esto se debe a que el paquete aparece dos veces: una 
vez para el origen que envía al destino y otra vez para el destino que recibe el paquete. Debido a que el origen y el 
destino son la misma interfaz (bucle invertido 127.0.0.1), Wireshark enumera el paquete dos veces.

    Frame 28: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 91, Ack: 122, Len: 1
    Telnet
        Data: c
    
    Frame 30: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 122, Ack: 92, Len: 1
    Telnet
        Data: i
    
    Frame 34: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 123, Ack: 93, Len: 1
    Telnet
        Data: s
    
    Frame 38: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 124, Ack: 94, Len: 1
    Telnet
        Data: c
    
    Frame 41: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 125, Ack: 95, Len: 1
    Telnet
        Data: o

n) Continúe haciendo clic en la flecha hacia abajo hasta que vea la Contraseña: en el campo Datos. Continúe presionando 
el botón flecha hacia abajo para leer los datos de los siguientes ocho paquetes que revelan, una letra a la vez, que la 
contraseña es la contraseña del usuario cisco

    Frame 47: 78 bytes on wire (624 bits), 78 bytes captured (624 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 98, Ack: 128, Len: 10
    Telnet
        Data: Password: 
    
    Frame 49: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 128, Ack: 108, Len: 1
    Telnet
        Data: p
    
    Frame 51: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 129, Ack: 108, Len: 1
    Telnet
        Data: a
    
    Frame 53: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 130, Ack: 108, Len: 1
    Telnet
        Data: s
    
    Frame 55: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 131, Ack: 108, Len: 1
    Telnet
        Data: s
    
    Frame 57: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 132, Ack: 108, Len: 1
    Telnet
        Data: w
    
    Frame 59: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 133, Ack: 108, Len: 1
    Telnet
        Data: o
    
    Frame 61: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 134, Ack: 108, Len: 1
    Telnet
        Data: r
    
    Frame 63: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 135, Ack: 108, Len: 1
    Telnet
        Data: d

o) Si continúa presionando la flecha hacia abajo a través del resto de los paquetes capturados, verá todo el texto 
enviado y recibido durante la sesión de Telnet, incluido su comando de salida y el mensaje de cierre de sesión.

    Frame 69: 430 bytes on wire (3440 bits), 430 bytes captured (3440 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 110, Ack: 138, Len: 362
    Telnet
        Data: Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-96-generic x86_64)\r\n
        Data: \r\n
        Data:  * Documentation:  https://help.ubuntu.com\r\n
        Data:  * Management:     https://landscape.canonical.com\r\n
        Data:  * Support:        https://ubuntu.com/advantage\r\n
        Data: \r\n
        Data: 0 updates can be applied immediately.\r\n
        Data: \r\n
        Data: \r\n
        Data: The list of available updates is more than a week old.\r\n
        Data: To check for new updates run: sudo apt update\r\n
    
    Frame 71: 118 bytes on wire (944 bits), 118 bytes captured (944 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 472, Ack: 138, Len: 50
    Telnet
        Data: Last login: Thu Mar 18 21:47:23 UTC 2021 on tty2\r\n
    
    Frame 73: 128 bytes on wire (1024 bits), 128 bytes captured (1024 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 522, Ack: 138, Len: 60
    Telnet
        Data: \033]0;cisco@labvm: ~\a\033[01;32mcisco@labvm\033[00m:\033[01;34m~\033[00m$ 
    
    Frame 116: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 138, Ack: 582, Len: 1
    Telnet
        Data: e
    
    Frame 120: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 139, Ack: 583, Len: 1
    Telnet
        Data: x
    
    Frame 124: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 140, Ack: 584, Len: 1
    Telnet
        Data: i
    
    Frame 127: 69 bytes on wire (552 bits), 69 bytes captured (552 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 57144, Dst Port: 23, Seq: 141, Ack: 585, Len: 1
    Telnet
        Data: t
    
    
    Frame 131: 78 bytes on wire (624 bits), 78 bytes captured (624 bits) on interface any, id 0
    Linux cooked capture
    Internet Protocol Version 4, Src: 127.0.0.1, Dst: 127.0.0.1
    Transmission Control Protocol, Src Port: 23, Dst Port: 57144, Seq: 586, Ack: 144, Len: 10
    Telnet
        Data: \r\n
        Data: logout\r\n

## Parte 4: Capturé y analicé el tráfico SSH cifrado

c) Para simular un inicio de sesión SSH, ingresé el comando ssh localhost. Si es la primera vez que usa el comando, el 
sistema le advierte sobre la autenticidad de localhost y le pregunta si desea continuar. Ingresé "yes", y luego
"password" como la contraseña para iniciar sesión.

    cisco@labvm:~$ ssh localhost
    The authenticity of host 'localhost (::1)' can't be established.
    ECDSA key fingerprint is SHA256:lEvtfM55v9O8L88uvZ4Em/UL4ARo8jWGE1hV8mVnDhQ.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added 'localhost' (ECDSA) to the list of known hosts.
    cisco@localhost's password: 
    Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-96-generic x86_64)

        * Documentation:  https://help.ubuntu.com
        * Management:     https://landscape.canonical.com
        * Support:        https://ubuntu.com/advantage

    0 updates can be applied immediately.


    The list of available updates is more than a week old.
    To check for new updates run: sudo apt update
    Last login: Mon Jan 31 01:17:10 2022 from localhost
    cisco@labvm:~$ 

d) Ingresé el comando exit para finalizar la sesión SSH.

    cisco@labvm:~$ exit
    logout
    Connection to localhost closed.
    cisco@labvm:~$ 

e) Regresé a Wireshark y detuve la captura. Si dejó telnet como término de búsqueda en Aplicar una pantalla
campo de filtro, no se listarán paquetes. Cambiar el término de búsqueda de telnet a ssh. Todos los paquetes de su 
sesión SSH ahora deberían mostrarse en el panel Lista de paquetes.

aca va la imagen 5

