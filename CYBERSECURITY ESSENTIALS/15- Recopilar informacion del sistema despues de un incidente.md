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


