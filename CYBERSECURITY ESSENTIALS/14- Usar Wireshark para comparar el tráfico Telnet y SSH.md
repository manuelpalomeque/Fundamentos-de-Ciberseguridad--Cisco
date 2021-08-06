## Paso 2: Exploré el analizador de protocolos Wireshark.

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






