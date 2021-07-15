1-2-a)Abrir el archivo maryftplogin.txt  y copiarlo

    U2FsdGVkX1+sKwL7uceALGKqAQ78WWown3ok73zicO8GLYu2SpMvLEwCB7HsyRC3MeimUjiXRCLwOSSahAraUrnEtkClGK4tytP9hludc6k=

1-2-e) Usar el siguiente comando para descifrar el contenido del archivo y revelar la información de inicio de sesión 
de FTP para Mary. Usar como contraseña maryftp123. Determinar el usuario y la contraseña-

    cisco@labvm:~$ echo 'U2FsdGVkX1+sKwL7uceALGKqAQ78WWown3ok73zicO8GLYu2SpMvLEwCB7HsyRC3MeimUjiXRCLw OSSahAraUrnEtkClGK4tytP9hludc6k=' | openssl aes-256-cbc -pbkdf2 -a -d 
    enter aes-256-cbc decryption password:
    Account Information:Mary Username= mary Password= cisco321

2-1-b) Abrir el archivo clientinfo.enc ¿En que estado estan los datos?

    U2FsdGVkX18uOvzW5lbgXcN7n3Z6qGIl+NcIpjbahVETpECh5F/Qi1mOSwSxF41V
    8zpmxPUXAINw9rPjst1K7AbghYhkVqsqIWVRHIqaBteBoFbk5+kZ2UWm8aMLjRt8
    qYIcwSSpCQbyEdOlKdVQrm9dTqHLf36Cg94Q7e+BZtH4HuGHp1MrkpG8MNVNcTjk
    r7D3d0sNaJzELETwlRCy2bIo8NS3ovm9+URQJ0K1HeUwhajjHbbPTlJx9kcfSLFY
    DR+R3HbWWHo8Kh2DC00+VBEUfi/w5hqkN5N0iZMsEGifba2vEGCvMSmx1yoXazWb
    kcrVnluEljsgcXyyDUnBAPVqdU3/9lWlrU9cD4T85oPchXg50blfSJ6rZiK8MQ9z
    NO9+ckZBXZs7JuvwOcfXL3KGZoPqlkwYsMi62CJivkusk49gyCcm4b35/VFnu/dZ
    4meP6IHK2pgzkXN3Eht0l5cL43TapkADT6+gZ2V/FMsx1MDVV85WWYie6pY7V3rS
    ST6rmDCvWwXTi3PIekj5y0yZhHopZ52B5FI0E7o/6Fw=

    Los datos estan encriptados.

2-2-c) Conectarse al servidor ftp de BR, usando las credenciales de mary que obtuvimos anteriormente

    C:\>ftp 10.0.3.30
    Trying to connect...10.0.3.30
    Connected to 10.0.3.30
    220- Welcome to PT Ftp server
    Username:mary
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>

2-3-c) Usar el comando dir para ver los archivos que estan en el servidor. Usar el comando put para
subir el archivo clientinfo.enc en el servidor, verificar con dir que el archivo se subio.

    ftp>dir
    
    Listing /ftp directory from 10.0.3.30: 
    0 : asa842-k8.bin 5571584
    1 : asa923-k8.bin 30468096
    2 : c1841-advipservicesk9-mz.124-15.T1.bin 33591768
    3 : c1841-ipbase-mz.123-14.T7.bin 13832032
    4 : c1841-ipbasek9-mz.124-12.bin 16599160
    5 : c1900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    6 : c2600-advipservicesk9-mz.124-15.T1.bin 33591768
    7 : c2600-i-mz.122-28.bin 5571584
    8 : c2600-ipbasek9-mz.124-8.bin 13169700
    9 : c2800nm-advipservicesk9-mz.124-15.T1.bin 50938004
    10 : c2800nm-advipservicesk9-mz.151-4.M4.bin 33591768
    11 : c2800nm-ipbase-mz.123-14.T7.bin 5571584
    12 : c2800nm-ipbasek9-mz.124-8.bin 15522644
    13 : c2900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    14 : c2950-i6q4l2-mz.121-22.EA4.bin 3058048
    15 : c2950-i6q4l2-mz.121-22.EA8.bin 3117390
    16 : c2960-lanbase-mz.122-25.FX.bin 4414921
    17 : c2960-lanbase-mz.122-25.SEE1.bin 4670455
    18 : c2960-lanbasek9-mz.150-2.SE4.bin 4670455
    19 : c3560-advipservicesk9-mz.122-37.SE1.bin 8662192
    20 : c3560-advipservicesk9-mz.122-46.SE.bin 10713279
    21 : c800-universalk9-mz.SPA.152-4.M4.bin 33591768
    22 : c800-universalk9-mz.SPA.154-3.M6a.bin 83029236
    23 : cat3k_caa-universalk9.16.03.02.SPA.bin 505532849
    24 : cgr1000-universalk9-mz.SPA.154-2.CG 159487552
    25 : cgr1000-universalk9-mz.SPA.156-3.CG 184530138
    26 : ir800-universalk9-bundle.SPA.156-3.M.bin 160968869
    27 : ir800-universalk9-mz.SPA.155-3.M 61750062
    28 : ir800-universalk9-mz.SPA.156-3.M 63753767
    29 : ir800_yocto-1.7.2.tar 2877440
    30 : ir800_yocto-1.7.2_python-2.7.3.tar 6912000
    31 : pt1000-i-mz.122-28.bin 5571584
    32 : pt3000-i6q4l2-mz.121-22.EA4.bin 3117390
    ftp>put clientinfo.enc
    
    Writing file clientinfo.enc to 10.0.3.30: 
    File transfer in progress...
    
    [Transfer complete - 564 bytes]
    
    564 bytes copied in 0.111 secs (5081 bytes/sec)
    ftp>dir
    
    Listing /ftp directory from 10.0.3.30: 
    0 : asa842-k8.bin 5571584
    1 : asa923-k8.bin 30468096
    2 : c1841-advipservicesk9-mz.124-15.T1.bin 33591768
    3 : c1841-ipbase-mz.123-14.T7.bin 13832032
    4 : c1841-ipbasek9-mz.124-12.bin 16599160
    5 : c1900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    6 : c2600-advipservicesk9-mz.124-15.T1.bin 33591768
    7 : c2600-i-mz.122-28.bin 5571584
    8 : c2600-ipbasek9-mz.124-8.bin 13169700
    9 : c2800nm-advipservicesk9-mz.124-15.T1.bin 50938004
    10 : c2800nm-advipservicesk9-mz.151-4.M4.bin 33591768
    11 : c2800nm-ipbase-mz.123-14.T7.bin 5571584
    12 : c2800nm-ipbasek9-mz.124-8.bin 15522644
    13 : c2900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    14 : c2950-i6q4l2-mz.121-22.EA4.bin 3058048
    15 : c2950-i6q4l2-mz.121-22.EA8.bin 3117390
    16 : c2960-lanbase-mz.122-25.FX.bin 4414921
    17 : c2960-lanbase-mz.122-25.SEE1.bin 4670455
    18 : c2960-lanbasek9-mz.150-2.SE4.bin 4670455
    19 : c3560-advipservicesk9-mz.122-37.SE1.bin 8662192
    20 : c3560-advipservicesk9-mz.122-46.SE.bin 10713279
    21 : c800-universalk9-mz.SPA.152-4.M4.bin 33591768
    22 : c800-universalk9-mz.SPA.154-3.M6a.bin 83029236
    23 : cat3k_caa-universalk9.16.03.02.SPA.bin 505532849
    24 : cgr1000-universalk9-mz.SPA.154-2.CG 159487552
    25 : cgr1000-universalk9-mz.SPA.156-3.CG 184530138
    26 : clientinfo.enc 564
    27 : ir800-universalk9-bundle.SPA.156-3.M.bin 160968869
    28 : ir800-universalk9-mz.SPA.155-3.M 61750062
    29 : ir800-universalk9-mz.SPA.156-3.M 63753767
    30 : ir800_yocto-1.7.2.tar 2877440
    31 : ir800_yocto-1.7.2_python-2.7.3.tar 6912000
    32 : pt1000-i-mz.122-28.bin 5571584
    33 : pt3000-i6q4l2-mz.121-22.EA4.bin 3117390
    ftp>quit
    
    221- Service closing control connection.
    C:\>

Si los actores de amenazas capturaran la transferencia de archivos, ¿qué sería en texto sin cifrar?
El nombre de usuario: mary, contraseña: cisco321 para la conexión FTP está en texto plano, pero el 
contenido del documento está encriptado.

3-2-a) Abrir y copiar el contenido del archivo bobftplogin.txt

    U2FsdGVkX1/+3jGTemCqs3e4dK8+b0xfXJiq4eoU0lQgRV9aZQPqJCBsYJWc9lDQwiB2svhiWSUVhCRS5qBrjgmDZF3q/dXqaCrZRR5prjE=


3-2-d) Desencriptar el contenido del archivo, para descubrir las credenciales de Bob. Usar como contraseña: bobftp123
.Cuales son las credenciales de Bob?

    cisco@labvm:~$ echo 'U2FsdGVkX1/+3jGTemCqs3e4dK8+b0xfXJiq4eoU0lQgRV9aZQPqJCBsYJWc9lDQwiB2svhiWSUV hCRS5qBrjgmDZF3q/dXqaCrZRR5prjE=' | openssl aes-256-cbc -pbkdf2 -a -d 
    enter aes-256-cbc decryption password:
    Account Information: Username= bob Password= ninja123

4-1-c) Conectarse al servidor ftp con las credenciales de Bob

    C:\>ftp 10.0.3.30
    Trying to connect...10.0.3.30
    Connected to 10.0.3.30
    220- Welcome to PT Ftp server
    Username:bob
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>

4-2-d) usar el comando dir para ver los archivos que estan subidos en el servidor. Con el comando
get descargar el archivo clientinfo.enc en la pc de Bob.

    C:\>ftp 10.0.3.30
    Trying to connect...10.0.3.30
    Connected to 10.0.3.30
    220- Welcome to PT Ftp server
    Username:bob
    331- Username ok, need password
    Password:
    230- Logged in
    (passive mode On)
    ftp>dir
    
    Listing /ftp directory from 10.0.3.30: 
    0 : asa842-k8.bin 5571584
    1 : asa923-k8.bin 30468096
    2 : c1841-advipservicesk9-mz.124-15.T1.bin 33591768
    3 : c1841-ipbase-mz.123-14.T7.bin 13832032
    4 : c1841-ipbasek9-mz.124-12.bin 16599160
    5 : c1900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    6 : c2600-advipservicesk9-mz.124-15.T1.bin 33591768
    7 : c2600-i-mz.122-28.bin 5571584
    8 : c2600-ipbasek9-mz.124-8.bin 13169700
    9 : c2800nm-advipservicesk9-mz.124-15.T1.bin 50938004
    10 : c2800nm-advipservicesk9-mz.151-4.M4.bin 33591768
    11 : c2800nm-ipbase-mz.123-14.T7.bin 5571584
    12 : c2800nm-ipbasek9-mz.124-8.bin 15522644
    13 : c2900-universalk9-mz.SPA.155-3.M4a.bin 33591768
    14 : c2950-i6q4l2-mz.121-22.EA4.bin 3058048
    15 : c2950-i6q4l2-mz.121-22.EA8.bin 3117390
    16 : c2960-lanbase-mz.122-25.FX.bin 4414921
    17 : c2960-lanbase-mz.122-25.SEE1.bin 4670455
    18 : c2960-lanbasek9-mz.150-2.SE4.bin 4670455
    19 : c3560-advipservicesk9-mz.122-37.SE1.bin 8662192
    20 : c3560-advipservicesk9-mz.122-46.SE.bin 10713279
    21 : c800-universalk9-mz.SPA.152-4.M4.bin 33591768
    22 : c800-universalk9-mz.SPA.154-3.M6a.bin 83029236
    23 : cat3k_caa-universalk9.16.03.02.SPA.bin 505532849
    24 : cgr1000-universalk9-mz.SPA.154-2.CG 159487552
    25 : cgr1000-universalk9-mz.SPA.156-3.CG 184530138
    26 : clientinfo.enc 564
    27 : ir800-universalk9-bundle.SPA.156-3.M.bin 160968869
    28 : ir800-universalk9-mz.SPA.155-3.M 61750062
    29 : ir800-universalk9-mz.SPA.156-3.M 63753767
    30 : ir800_yocto-1.7.2.tar 2877440
    31 : ir800_yocto-1.7.2_python-2.7.3.tar 6912000
    32 : pt1000-i-mz.122-28.bin 5571584
    33 : pt3000-i6q4l2-mz.121-22.EA4.bin 3117390
    ftp>get clientinfo.enc
    
    Reading file clientinfo.enc from 10.0.3.30: 
    File transfer in progress...
    
    [Transfer complete - 564 bytes]
    
    564 bytes copied in 0.057 secs (9894 bytes/sec)
    ftp>

5-1-b) Verificar los Emails, ¿Cual es la clave de descifrado?

    The decryption key is cisco123

5-2-c) Abrir el archivo clientinfo.enc y copiar su contenido

    U2FsdGVkX18uOvzW5lbgXcN7n3Z6qGIl+NcIpjbahVETpECh5F/Qi1mOSwSxF41V
    8zpmxPUXAINw9rPjst1K7AbghYhkVqsqIWVRHIqaBteBoFbk5+kZ2UWm8aMLjRt8
    qYIcwSSpCQbyEdOlKdVQrm9dTqHLf36Cg94Q7e+BZtH4HuGHp1MrkpG8MNVNcTjk
    r7D3d0sNaJzELETwlRCy2bIo8NS3ovm9+URQJ0K1HeUwhajjHbbPTlJx9kcfSLFY
    DR+R3HbWWHo8Kh2DC00+VBEUfi/w5hqkN5N0iZMsEGifba2vEGCvMSmx1yoXazWb
    kcrVnluEljsgcXyyDUnBAPVqdU3/9lWlrU9cD4T85oPchXg50blfSJ6rZiK8MQ9z
    NO9+ckZBXZs7JuvwOcfXL3KGZoPqlkwYsMi62CJivkusk49gyCcm4b35/VFnu/dZ
    4meP6IHK2pgzkXN3Eht0l5cL43TapkADT6+gZ2V/FMsx1MDVV85WWYie6pY7V3rS
    ST6rmDCvWwXTi3PIekj5y0yZhHopZ52B5FI0E7o/6Fw=

5-2-h) En la maquina virtual verificar que el archivo clientinfo.enc este en el directorio local

    cisco@labvm:~$ ls 
    clientinfo.enc  Desktop  Documents  Downloads  income.txt  lynis

5-2-k) desencriptar el archivo clientinfo.enc. Usar la contrasela descubierta anteriormente de Mary.
Luego verificar que se haya creado el nuevo archivo en el directorio

    cisco@labvm:~$ openssl aes-256-cbc -pbkdf2 -a -d -in clientinfo.enc -out clientinfo.txt 
    enter aes-256-cbc decryption password:
    cisco@labvm:~$ ls
    clientinfo.enc  Desktop    Downloads   lynis
    clientinfo.txt  Documents  income.txt

5-2-l) abrir el archivo clientinfo.txt  para ver su contenido desencriptado

    cisco@labvm:~$ cat clientinfo.txt
    Name|Address|Credit Card
    
    Drew N. Stark|40008|532605 072104 7364
    Laith Wilkerson|21800|516234 6483327961
    Drew A. Dennis|33024|4716904313886
    Genevieve Robertson|25498|491 65497 20952 457
    Paki Parsons|419043|492954 7171363013
    Teagan N. Avery|64416|4485 5676 5330 3713
    Joy B. Goodman|6048TB|419978 0389706805
    Orla L. Rowe|93081|520 88110 11661 765
    Wynter English|1396|534047 781153 0565


