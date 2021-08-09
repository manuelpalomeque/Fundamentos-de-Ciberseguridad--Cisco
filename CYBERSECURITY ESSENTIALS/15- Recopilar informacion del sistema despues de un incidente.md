## Parte 2: recopilar información volátil del sistema comprometido

En este paso, creé un archivo llamado report.txt que incluye una variedad de información del sistema que se puede usar 
para el análisis de incidentes. Luego, este informe puede transferirse a una unidad USB, enviarse por correo electrónico
o cargarse en un servidor en la nube para conservar la información. Entonces el sistema puede ser desmantelado.

a) Cambié al usuario root con el comando sudo su. Ingresé  password como la contraseña.
    
    cisco@labvm:~$ sudo su
    [sudo] password for cisco: 
    root@labvm:/home/cisco# 

b) Ingrese el comando echo y luego especifique un encabezado para un archivo recién creado llamado report.txt. Ingresé
el comando cat para revisar el nuevo archivo.

    root@labvm:/home/cisco# echo Reporte de Investigacion de incidente > report.txt
    root@labvm:/home/cisco# cat report.txt
    Reporte de Investigacion de incidente
    root@labvm:/home/cisco# 

c) Ingresé el comando date y redirija la fecha y la marca de tiempo al archivo report.txt. Asegurandome de usar 
corchetes angulares dobles (>>) para agregar al archivo report.txt. De lo contrario, reemplazará el contenido anterior.

Nota: Para documentar mejor el contenido almacenado en report.txt, use el comando echo para agregar un subtítulo, para 
Fecha y hora de inicio. Cada subpaso especificará un subtítulo para que lo agregue antes de recopilar información
    
    root@labvm:/home/cisco# echo =====Start Date and Time===== >> report.txt
    root@labvm:/home/cisco# date >> report.txt
    root@labvm:/home/cisco# 

d) Ingresé el comando uname para imprimir la información del sistema. Use la opción -a para agregar todo el sistema
información al archivo report.txt

    root@labvm:/home/cisco# echo =====System Information===== >> report.txt
    root@labvm:/home/cisco# uname -a >> report.txt
    root@labvm:/home/cisco# 

e) Ingresé el comando ifconfig -a y agregue toda la información de la interfaz de red al archivo report.txt.

    root@labvm:/home/cisco# echo =====Network Interfaces===== >> report.txt
    root@labvm:/home/cisco# ifconfig -a >> report.txt
    root@labvm:/home/cisco# 

f) El comando netstat puede recopilar todas las estadísticas de la red. Ingrese el comando con las opciones -ano para 
recopilar datos en todos los sockets (-a), direcciones IP en lugar de nombres de dominio (-n) e información relacionada
con los tiempos de red (-o). Agregue la salida al archivo report.txt.

    root@labvm:/home/cisco# echo =====Network Statistics===== >> report.txt
    root@labvm:/home/cisco# netstat -ano >> report.txt
    root@labvm:/home/cisco# 

g) El comando ps informa una instantánea de los procesos actuales que se ejecutan en el sistema. Introducí el
comando con las opciones -axu para enumerar todos los procesos que se ejecutan en el sistema (-a y -x) y en un formato 
orientado al usuario (-u). Agregue la salida al archivo report.txt

    root@labvm:/home/cisco# echo =====Processes===== >> report.txt
    root@labvm:/home/cisco# ps axu >> report.txt
    root@labvm:/home/cisco# 

h) El comando route enumera la tabla de enrutamiento utilizada actualmente por el sistema. Ingrese el comando con la 
opción -n para enumerar las direcciones IP en lugar de intentar determinar los nombres de host. Agregue la salida al 
archivo report.txt

    root@labvm:/home/cisco# echo =====Routing Table===== >> report.txt
    root@labvm:/home/cisco# route -n >> report.txt
    root@labvm:/home/cisco

i) Ingresé el comando date y agregue la fecha y la marca de tiempo al final del archivo para completar el informe.

    root@labvm:/home/cisco# echo =====End Date and Time===== >> report.txt
    root@labvm:/home/cisco# date >> report.txt
    root@labvm:/home/cisco# 

j) Usé el comando cat y canalice la salida al comando less para ver report.txt una página o línea a la vez. Presioné la 
barra espaciadora para desplazarme hacia abajo por página, o Enter para desplazarse hacia abajo por una sola línea. 
Escribi q cuando termine.

    Reporte de Investigacion de incidente
    =====Start Date and Time=====
    Mon 31 Jan 2022 02:28:38 PM UTC
    
    =====System Information=====
    Linux labvm 5.4.0-96-generic #109-Ubuntu SMP Wed Jan 12 16:49:16 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
    
    =====Network Interfaces=====
    enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
            inet6 fe80::a00:27ff:fec7:750b  prefixlen 64  scopeid 0x20<link>
            ether 08:00:27:c7:75:0b  txqueuelen 1000  (Ethernet)
            RX packets 5  bytes 1571 (1.5 KB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 62  bytes 7398 (7.3 KB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
            inet 127.0.0.1  netmask 255.0.0.0
            inet6 ::1  prefixlen 128  scopeid 0x10<host>
            loop  txqueuelen 1000  (Local Loopback)
            RX packets 28  bytes 2858 (2.8 KB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 28  bytes 2858 (2.8 KB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    =====Network Statistics=====
    Active Internet connections (servers and established)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State       Timer
    tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      off (0.00/0/0)
    tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      off (0.00/0/0)
    tcp        0      0 0.0.0.0:23              0.0.0.0:*               LISTEN      off (0.00/0/0)
    tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      off (0.00/0/0)
    tcp6       0      0 :::22                   :::*                    LISTEN      off (0.00/0/0)
    tcp6       0      0 ::1:631                 :::*                    LISTEN      off (0.00/0/0)
    udp        0      0 0.0.0.0:5353            0.0.0.0:*                           off (0.00/0/0)
    udp        0      0 0.0.0.0:57102           0.0.0.0:*                           off (0.00/0/0)
    udp        0      0 127.0.0.53:53           0.0.0.0:*                           off (0.00/0/0)
    udp        0      0 10.0.2.15:68            0.0.0.0:*                           off (0.00/0/0)
    udp        0      0 0.0.0.0:631             0.0.0.0:*                           off (0.00/0/0)
    udp6       0      0 :::36002                :::*                                off (0.00/0/0)
    udp6       0      0 :::5353                 :::*                                off (0.00/0/0)
    raw6       0      0 :::58                   :::*                    7           off (0.00/0/0)
    Active UNIX domain sockets (servers and established)
    Proto RefCnt Flags       Type       State         I-Node   Path
    unix  2      [ ACC ]     SEQPACKET  LISTENING     243      /run/udev/control
    unix  2      [ ]         DGRAM                    20411    /run/user/900/systemd/notify
    unix  2      [ ACC ]     STREAM     LISTENING     20414    /run/user/900/systemd/private
    unix  2      [ ACC ]     STREAM     LISTENING     20419    /run/user/900/bus
    unix  2      [ ACC ]     STREAM     LISTENING     20420    /run/user/900/gnupg/S.dirmngr
    
    =====Processes=====
    USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root           1  0.0  0.2 101856 11356 ?        Ss   14:14   0:00 /sbin/init
    root           2  0.0  0.0      0     0 ?        S    14:14   0:00 [kthreadd]
    root           3  0.0  0.0      0     0 ?        I<   14:14   0:00 [rcu_gp]
    root           4  0.0  0.0      0     0 ?        I<   14:14   0:00 [rcu_par_gp]
    root           5  0.0  0.0      0     0 ?        I    14:14   0:00 [kworker/0:0-events]
    root           6  0.0  0.0      0     0 ?        I<   14:14   0:00 [kworker/0:0H-kblockd]
    root           9  0.0  0.0      0     0 ?        I<   14:14   0:00 [mm_percpu_wq]
    root          10  0.0  0.0      0     0 ?        S    14:14   0:00 [ksoftirqd/0]
    root          11  0.0  0.0      0     0 ?        I    14:14   0:00 [rcu_sched]
    root          12  0.0  0.0      0     0 ?        S    14:14   0:00 [migration/0]
    root          13  0.0  0.0      0     0 ?        S    14:14   0:00 [idle_inject/0]
    root          14  0.0  0.0      0     0 ?        S    14:14   0:00 [cpuhp/0]
    root          15  0.0  0.0      0     0 ?        S    14:14   0:00 [cpuhp/1]
    root          16  0.0  0.0      0     0 ?        S    14:14   0:00 [idle_inject/1]
    
    =====Routing Table=====
    Kernel IP routing table
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
    0.0.0.0         10.0.2.2        0.0.0.0         UG    100    0        0 enp0s3
    10.0.2.0        0.0.0.0         255.255.255.0   U     0      0        0 enp0s3
    10.0.2.2        0.0.0.0         255.255.255.255 UH    100    0        0 enp0s3
    =====End Date and Time=====
    Mon 31 Jan 2022 02:39:22 PM UTC
    (END)



