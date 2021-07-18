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

## 2) ejecutar John the Ripper para recuperar las contraseñas:

a)  Para ver que las contraseñas aun no estan recuperadas (crakeadas), use el siguiente comando:

    cisco@labvm:~/Downloads/john/run$ ./john --show mypasswd
    Created directory: /home/cisco/.john
    0 password hashes cracked, 5 left
    cisco@labvm:~/Downloads/john/run$ 

b) Usando el diccionario password.lst el cual esta predefinido en John the Ripper, con un conjunto de estandares de 
reglas para utilizar el diccionario y recuperar todos los hash de contraseñas de tipo md5crypt y crypt.

    cisco@labvm:~/Downloads/john/run$ ./john --wordlist=password.lst --rules 
    mypasswd --format=crypt
    Loaded 5 password hashes with 5 different salts (crypt, generic crypt(3) [?/64])
    Press 'q' or Ctrl-C to abort, almost any other key for status
    password1 (Eric)
    password (cisco)
    password (Eve)
    12345 (Bob)
    123456 (Alice)
    5g 0:00:00:00 100% 6.097g/s 117.0p/s 585.3c/s 585.3C/s #CSE course accounts from Lab -
    Authentication Authorization Accounting..natasha
    Use the "--show" option to display all of the cracked passwords reliably
    Session completed
    cisco@labvm:~/Downloads/john/run$



c) Usar el comando ./john --show mypasswd de nuevo para ver que contraseñas fueron creakeadas

    cisco@labvm:~/Downloads/john/run$ ./john --show mypasswd
    cisco:password:900:900:Cybersecurity Analyst,,,:/home/cisco:/bin/bash
    Alice:123456:1000:1000::/home/Alice:/bin/bash
    Bob:12345:1001:1001::/home/Bob:/bin/bash
    Eve:password:1002:1002::/home/Eve:/bin/bash
    Eric:password1:1003:1003::/home/Eric:/bin/bash
    5 password hashes cracked, 0 left
    cisco@labvm:~/Downloads/john/run$

## 3) cambie la contraseña de un usuario a una versión más segura e intente recuperarla

a) Busqué un comprobador de seguridad de contraseñas online, para probar la contraseña que elegi:

    https://password.kaspersky.com/es/

Ejemplo de contraseña: Agosto*Es*El*Mejor*Mes!2022

b) Cambiae la contraseña del usuario Eric:

    cisco@labvm:~/Downloads/john/run$ sudo passwd Eric
    [sudo] password for cisco: 
    New password: 
    Retype new password: 
    passwd: password updated successfully
    cisco@labvm:~/Downloads/john/run$ 

