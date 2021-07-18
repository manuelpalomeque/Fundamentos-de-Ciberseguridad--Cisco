## 1) Crear un grupo de usuarios:

a) Escalar privilegios a el nivel root, usando "password" como contraseña:

    cisco@labvm:~$ sudo su
    [sudo] password for cisco: 
    root@labvm:/home/cisco#

b) Agregar un nuevo grupo llamado HR:

    root@labvm:/home/cisco# groupadd HR

c) Verificar que el nuevo grupo se agrego:

    root@labvm:/home/cisco# cat /etc/group
    root:x:0:
    daemon:x:1:
    bin:x:2:
    sys:x:3:
    adm:x:4:syslog
    tty:x:5:syslog
    disk:x:6:
    lp:x:7:
    mail:x:8:
    news:x:9:
    uucp:x:10:
    man:x:12:
    proxy:x:13:
    kmem:x:15:
    dialout:x:20:
    fax:x:21:
    voice:x:22:
    cdrom:x:24:
    floppy:x:25:
    tape:x:26:
    sudo:x:27:cisco
    audio:x:29:pulse
    dip:x:30:
    www-data:x:33:
    backup:x:34:
    operator:x:37:
    list:x:38:
    irc:x:39:
    src:x:40:
    gnats:x:41:
    shadow:x:42:
    utmp:x:43:telnetd
    video:x:44:
    sasl:x:45:
    plugdev:x:46:
    staff:x:50:
    games:x:60:
    users:x:100:
    nogroup:x:65534:
    systemd-journal:x:101:
    systemd-network:x:102:
    systemd-resolve:x:103:
    systemd-timesync:x:104:
    crontab:x:105:
    messagebus:x:106:
    input:x:107:
    kvm:x:108:
    render:x:109:
    syslog:x:110:
    uuidd:x:111:
    tcpdump:x:112:
    ssh:x:113:
    cisco:x:900:
    lpadmin:x:114:
    sambashare:x:115:
    systemd-coredump:x:999:
    tss:x:116:
    bluetooth:x:117:
    ssl-cert:x:118:
    netdev:x:119:
    lightdm:x:120:
    nopasswdlogin:x:121:
    rtkit:x:122:
    avahi-autoipd:x:123:
    whoopsie:x:124:
    avahi:x:125:
    scanner:x:127:saned
    saned:x:128:
    colord:x:129:
    pulse:x:130:
    pulse-access:x:131:
    vboxsf:x:998:cisco
    wireshark:x:126:cisco
    telnetd:x:132:
    Alice:x:1000:
    Bob:x:1001:
    Eve:x:1002:
    Eric:x:1003:
    Xnobody:x:1004:
    HR:x:1005:

El nuevo grupo HR se muestra en la parte inferior del archivo /etc/group con un ID de grupo de 1005.

## 2) Agregar usuarios al nuevo grupo

a) Agregar la nueva usuario Jenny:
contraseña: jenPass
Nombre completo: Jenny

    root@labvm:/home/cisco# adduser jenny
    Adding user `jenny' ...
    Adding new group `jenny' (1006) ...
    Adding new user `jenny' (1005) with group `jenny' ...
    Creating home directory `/home/jenny' ...
    Copying files from `/etc/skel' ...
    New password: 
    Retype new password: 
    passwd: password updated successfully
    Changing the user information for jenny
    Enter the new value, or press ENTER for the default
        Full Name []: Jenny
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
    Is the information correct? [Y/n] Y

b) Mover el usuario jenny al grupo HR:

    root@labvm:/home/cisco# usermod -G HR jenny

c)Agregar el nuevo usuario Joe:
contraseña: joePass
Nombre completo: Joe


    root@labvm:/home/cisco# adduser joe
    Adding user `joe' ...
    Adding new group `joe' (1007) ...
    Adding new user `joe' (1006) with group `joe' ...
    Creating home directory `/home/joe' ...
    Copying files from `/etc/skel' ...
    New password: 
    Retype new password: 
    passwd: password updated successfully
    Changing the user information for joe
    Enter the new value, or press ENTER for the default
        Full Name [Joe]: Joe
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
    Is the information correct? [Y/n] Y

d) Mover el usuario Joe al grupo HR:

    root@labvm:/home/cisco# usermod -G HR joe

e) verificar que los usuarios fueron agregados:

    root@labvm:/home/cisco# cat /etc/passwd
    root:x:0:0:root:/root:/bin/bash
    daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
    bin:x:2:2:bin:/bin:/usr/sbin/nologin
    sys:x:3:3:sys:/dev:/usr/sbin/nologin
    sync:x:4:65534:sync:/bin:/bin/sync
    games:x:5:60:games:/usr/games:/usr/sbin/nologin
    man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
    lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
    mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
    news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
    uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
    proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
    www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
    backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
    list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
    irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
    gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
    nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
    systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
    systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
    systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
    messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
    syslog:x:104:110::/home/syslog:/usr/sbin/nologin
    _apt:x:105:65534::/nonexistent:/usr/sbin/nologin
    uuidd:x:106:111::/run/uuidd:/usr/sbin/nologin
    tcpdump:x:107:112::/nonexistent:/usr/sbin/nologin
    sshd:x:108:65534::/run/sshd:/usr/sbin/nologin
    cisco:x:900:900:Cybersecurity Analyst,,,:/home/cisco:/bin/bash
    systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
    tss:x:109:116:TPM software stack,,,:/var/lib/tpm:/bin/false
    lightdm:x:110:120:Light Display Manager:/var/lib/lightdm:/bin/false
    rtkit:x:111:122:RealtimeKit,,,:/proc:/usr/sbin/nologin
    dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
    avahi-autoipd:x:113:123:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
    usbmux:x:114:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
    kernoops:x:115:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
    whoopsie:x:116:124::/nonexistent:/bin/false
    avahi:x:117:125:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
    cups-pk-helper:x:118:114:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
    speech-dispatcher:x:120:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
    saned:x:121:128::/var/lib/saned:/usr/sbin/nologin
    hplip:x:122:7:HPLIP system user,,,:/run/hplip:/bin/false
    colord:x:123:129:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
    pulse:x:124:130:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
    vboxadd:x:998:1::/var/run/vboxadd:/bin/false
    telnetd:x:119:132::/nonexistent:/usr/sbin/nologin
    Alice:x:1000:1000::/home/Alice:/bin/bash
    Bob:x:1001:1001::/home/Bob:/bin/bash
    Eve:x:1002:1002::/home/Eve:/bin/bash
    Eric:x:1003:1003::/home/Eric:/bin/bash
    Xnobody:x:1004:1004::/home/Xnobody:/bin/sh
    jenny:x:1005:1006:Jenny,,,:/home/jenny:/bin/bash
    joe:x:1006:1007:Joe,,,\:/home/joe:/bin/bash

f) Ver los usuarios creados en shadows files

    root@labvm:/home/cisco# cat /etc/shadow
    root:!:18704:0:99999:7:::
    daemon:*:18704:0:99999:7:::
    bin:*:18704:0:99999:7:::
    sys:*:18704:0:99999:7:::
    sync:*:18704:0:99999:7:::
    games:*:18704:0:99999:7:::
    man:*:18704:0:99999:7:::
    lp:*:18704:0:99999:7:::
    mail:*:18704:0:99999:7:::
    news:*:18704:0:99999:7:::
    uucp:*:18704:0:99999:7:::
    proxy:*:18704:0:99999:7:::
    www-data:*:18704:0:99999:7:::
    backup:*:18704:0:99999:7:::
    list:*:18704:0:99999:7:::
    irc:*:18704:0:99999:7:::
    gnats:*:18704:0:99999:7:::
    nobody:*:18704:0:99999:7:::
    systemd-network:*:18704:0:99999:7:::
    systemd-resolve:*:18704:0:99999:7:::
    systemd-timesync:*:18704:0:99999:7:::
    messagebus:*:18704:0:99999:7:::
    syslog:*:18704:0:99999:7:::
    _apt:*:18704:0:99999:7:::
    uuidd:*:18704:0:99999:7:::
    tcpdump:*:18704:0:99999:7:::
    sshd:*:18704:0:99999:7:::
    cisco:$6$l7olThjiHtJnqYDq$cNod6gyQebmJWRZU7oUnTcifdttFyo07X7BFkM1DsGj42DJlywi5I490.H/qrYDjO5aAlN/dLKi7knsKzUWkN/:18704:0:99999:7:::
    systemd-coredump:!!:18704::::::
    tss:*:18704:0:99999:7:::
    lightdm:*:18704:0:99999:7:::
    rtkit:*:18704:0:99999:7:::
    dnsmasq:*:18704:0:99999:7:::
    avahi-autoipd:*:18704:0:99999:7:::
    usbmux:*:18704:0:99999:7:::
    kernoops:*:18704:0:99999:7:::
    whoopsie:*:18704:0:99999:7:::
    avahi:*:18704:0:99999:7:::
    cups-pk-helper:*:18704:0:99999:7:::
    speech-dispatcher:!:18704:0:99999:7:::
    saned:*:18704:0:99999:7:::
    hplip:*:18704:0:99999:7:::
    colord:*:18704:0:99999:7:::
    pulse:*:18704:0:99999:7:::
    vboxadd:!:18704::::::
    telnetd:*:18704:0:99999:7:::
    Alice:$6$boix6HtlvyyjJ226$Ru/nakW8avxYk5CTaV8I1VZYTqz8JYvrkXP28GugR0.44pqQROUBk/Y13BCJCrNfsKKGgtALzkedJ4gremKup0:18704:0:99999:7:::
    Bob:$6$BBxFfR7DqGarNIY5$os.gsp1NSm54Hn1I0fzz/eoG8uQZ2S/naCSuUA65BWPUpLTYC4zQRwwH1emO392w3A5pfCu/CkGz5sqrIICRs.:18704:0:99999:7:::
    Eve:$6$d4TOWXQNL5Gj9SsP$vWklwbtAZmoBDw83MQS8fghBcf4BIQuBQzvGqVfivXDxeuWmhmjvc7uMcz1OQcMCFSB/2HL2sONGnxsuQehki/:18704:0:99999:7:::
    Eric:$6$c.O3iOCcwC0lh8wh$cqg2Uu/OI46SVitMR4hJU1hinMSpaMx3LteHdoSfM5NvhQQ8SB1YJAKeLTJAEu7w3Ragjm86DQ6KBr5BquKKI0:18704:0:99999:7:::
    Xnobody:!:18704:0:99999:7:::
    jenny:$6$hBtHzC3thRxOJpua$BYI.YAURxSMPirPGrCMeELDguKC8I5mEelbbY.soLxwDgBAr3UuBkRihDlf2L.4QsBWJLGsQnYA4V7CKMW4uH/:19014:0:99999:7:::
    joe:$6$fcE1KzR2WKYblqQL$0FtdhD6GFQdYtyNlC6w37HJEPAKlkHu7RrrO0JkkCOmwQ43HKjkawWZUdB9qqDjGMKsN5JqYWV32JM/Tt5dTF/:19014:0:99999:7:::
   
## 3) Cambiar usuarios y modificar permisos:

a) Cambie de usuario Cisco a Jenny. Use pwd para verificar el directorio actual, luego accedi al directorio /home con 
cd ../..

    jenny@labvm:~$ dir
    Desktop  Documents  Downloads
    jenny@labvm:~$ cd Desktop
    jenny@labvm:~/Desktop$ pwd
    /home/jenny/Desktop
    jenny@labvm:~/Desktop$ cd ../..
    jenny@labvm:/home$ 

b) Use el comando ls -l para ver los directorios, permisos y usuarios.

    jenny@labvm:/home$ ls -l
    total 28
    drwxr-xr-x  2 Alice Alice 4096 Mar 18  2021 Alice
    drwxr-xr-x  2 Bob   Bob   4096 Mar 18  2021 Bob
    drwxr-xr-x 10 cisco cisco 4096 Jan 22 22:39 cisco
    drwxr-xr-x  2 Eric  Eric  4096 Mar 18  2021 Eric
    drwxr-xr-x  2 Eve   Eve   4096 Mar 18  2021 Eve
    drwxr-xr-x  9 jenny jenny 4096 Jan 22 23:54 jenny
    drwxr-xr-x  2 joe   joe   4096 Jan 22 22:42 joe

c) Entre a la carpeta de Joe con el comando cd, pude hacerlo porque el permiso para otros es r-x. La x permite que 
cualquier persona ingrese al directorio.

    jenny@labvm:/home$ cd joe
    jenny@labvm:/home/joe$

d) Intente crear un nuevo archivo en la carpeta de joe, pero no pude hacerlo porque no tengo los permisos para escribir 
en la carpeta de joe.

    jenny@labvm:/home/joe$ touch new.txt
    touch: cannot touch 'new.txt': Permission denied

e) Sali de la carpeta de joe e ingrese como el usuario Cisco, con la contraseña "password"

    jenny@labvm:/home/joe$ cd ..
    jenny@labvm:/home$ su cisco
    Password: 
    cisco@labvm:/home$

f) Cambie a root

    cisco@labvm:/home$ sudo -i
    [sudo] password for cisco: 
    root@labvm:~#

g) MOdifique los permisos para el directorio de Joe:

    root@labvm:~# cd /home
    root@labvm:/home# chmod o-x joe
    root@labvm:/home# ls -l
    total 28
    drwxr-xr-x  2 Alice Alice 4096 Mar 18  2021 Alice
    drwxr-xr-x  2 Bob   Bob   4096 Mar 18  2021 Bob
    drwxr-xr-x 10 cisco cisco 4096 Jan 22 22:39 cisco
    drwxr-xr-x  2 Eric  Eric  4096 Mar 18  2021 Eric
    drwxr-xr-x  2 Eve   Eve   4096 Mar 18  2021 Eve
    drwxr-xr-x  9 jenny jenny 4096 Jan 22 23:54 jenny
    drwxr-xr--  2 joe   joe   4096 Jan 22 22:42 joe

h) Me desloguee de root y de cisco. Ingrese el comando cd joe para intentar navegar al directorio de Joe, pero se 
deniega el acceso.

    root@labvm:/home# exit
    logout
    cisco@labvm:/home$ exit
    exit
    jenny@labvm:/home$ cd joe
    bash: cd: joe: Permission denied

