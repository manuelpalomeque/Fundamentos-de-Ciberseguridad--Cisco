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

