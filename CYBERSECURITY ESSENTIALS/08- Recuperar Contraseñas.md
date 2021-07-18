## 1) Combinar contraseñas y usuarios en un archivo de texto:

a) Me posicione en la carpeta donde esta localizado John the Ripper

    cisco@labvm:~$ cd Downloads/john/run
    cisco@labvm:~/Downloads/john/run$ 

b) Use el comando unshadow para combinat el archivo /etc/passwd donde las cuentas de usuario estan guardadas, con el 
archivo /etc/shadow donde las contraseñas de los usuarios estan guardados. Para asi crear un nuevo archivo llamado
mypasswd 

    cisco@labvm:~/Downloads/john/run$ sudo ./unshadow /etc/passwd /etc/shadow > mypasswd
    [sudo] password for cisco: 
    cisco@labvm:~/Downloads/john/run$ 
