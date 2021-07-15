1-2-a)Abrir el archivo maryftplogin.txt  y copiarlo

    U2FsdGVkX1+sKwL7uceALGKqAQ78WWown3ok73zicO8GLYu2SpMvLEwCB7HsyRC3MeimUjiXRCLwOSSahAraUrnEtkClGK4tytP9hludc6k=

1-2-e) Usar el siguiente comando para descifrar el contenido del archivo y revelar la información de inicio de sesión 
de FTP para Mary. Usar como contraseña maryftp123. Determinar el usuario y la contraseña-

    cisco@labvm:~$ echo 'U2FsdGVkX1+sKwL7uceALGKqAQ78WWown3ok73zicO8GLYu2SpMvLEwCB7HsyRC3MeimUjiXRCLw OSSahAraUrnEtkClGK4tytP9hludc6k=' | openssl aes-256-cbc -pbkdf2 -a -d 
    enter aes-256-cbc decryption password:
    Account Information:Mary Username= mary Password= cisco321

