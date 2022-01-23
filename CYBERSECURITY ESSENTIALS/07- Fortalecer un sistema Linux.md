## 1) Examine la versión actual de Lynis.

a) Me posicione sobre la carpeta de Lynis e ingrese el compando sudo ./lynis update info, para verificar la informacion 
de Lynis (ver la version y descargas para la herramienta). Como contraseña use password.

    cisco@labvm:~$ cd Downloads/lynis
    cisco@labvm:~/Downloads/lynis$ sudo ./lynis update info
    [sudo] password for cisco: 
    
     == Lynis ==
    
      Version            : 3.0.3
      Status             : Outdated
      Installed version  : 303
      Latest version     : 307
      Release date       : 2021-01-07
      Project page       : https://cisofy.com/lynis/
      Source code        : https://github.com/CISOfy/lynis
      Latest package     : https://packages.cisofy.com/
    
    
    2007-2021, CISOfy - https://cisofy.com/lynis/

En este caso, tengo la version 303, cuando ya esta disponible la 307, por ello me indica que es una version anticuada.
Debo actualizarla


