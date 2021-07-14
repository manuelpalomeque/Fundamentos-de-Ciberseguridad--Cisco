1-2-c)Los archivos más recientes y sus hashes:

        FileName | NEclients.txt | Hash| 4dff78485308281b339bfda9236eda45
        FileName | NWclients.txt | Hash| 2c77ff70d5f7a2a720d231617157faa4
        FileName | Nclients.txt | Hash| 8040e56207aab9dd331566b79dca37dd
        FileName | SEclients.txt | Hash| 520eb6c72cc2574decb731bc6230e223
        FileName | SWclients.txt | Hash| 69e751fe1175b39709629710e5ffa491
        FileName | Sclients.txt | Hash| 06bea9b0fa7db92d7c21261b88323be6
        FileName | income.txt | Hash| b138706cb55787d2a01934b224edad32203f87470ff6c7ffb9bd126786d1830d


1-3)Descargar los archivos de respaldo a la PC de Mike

        C:\>ftp hq.corp
        Trying to connect...hq.corp
        Connected to hq.corp
        220- Welcome to PT Ftp server
        Username:mike
        331- Username ok, need password
        Password:
        230- Logged in
        (passive mode On)
        ftp>dir
        
        Listing /ftp directory from hq.corp: 
        0 : NEclients.txt 582
        1 : NWclients.txt 583
        2 : Nclients.txt 698
        3 : SEclients.txt 597
        4 : SWclients.txt 649
        5 : Sclients.txt 780
        ftp>get NEclients.txt
        
        Reading file NEclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 582 bytes]
        
        582 bytes copied in 0.055 secs (10581 bytes/sec)
        ftp>get NWclients.txt
        
        Reading file NWclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 583 bytes]
        
        583 bytes copied in 0.029 secs (20103 bytes/sec)
        ftp>get Nclients.txt
        
        Reading file Nclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 698 bytes]
        
        698 bytes copied in 0.025 secs (27920 bytes/sec)
        ftp>get SEclients.txt
        
        Reading file SEclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 597 bytes]
        
        597 bytes copied in 0.025 secs (23880 bytes/sec)
        ftp>get SWclients.txt
        
        Reading file SWclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 649 bytes]
        
        649 bytes copied in 0.026 secs (24961 bytes/sec)
        ftp>get Sclients.txt
        
        Reading file Sclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 780 bytes]
        
        780 bytes copied in 0.022 secs (35454 bytes/sec)
        ftp>quit
        
        221- Service closing control connection.
        C:\>dir
        Volume in drive C has no label.
        Volume Serial Number is 5E12-4AF3
        Directory of C:\
        
        12/31/1969 21:0 PM 582 NEclients.txt 
        12/31/1969 21:0 PM 583 NWclients.txt 
        12/31/1969 21:0 PM 698 Nclients.txt 
        12/31/1969 21:0 PM 597 SEclients.txt 
        12/31/1969 21:0 PM 649 SWclients.txt 
        12/31/1969 21:0 PM 780 Sclients.txt 
        3889 bytes 6 File(s)

2-1-b)Abrir y copiar el contenido de NEclients.txt:

        Name|Zip Code|Email|Pin #
        
        Hannah Caldwell|7624|nec@ligula.net|6111
        Rhiannon B. Langley|46872|fermentum@cursusnon.co.uk|9781
        Nigel Ward|3584|convallis.erat.eget@luctusvulputatenisi.org|4896
        Alvin Farley|69508|lectus@volutpat.co.uk|5358
        Clark U. Pratt|23441|tincidunt.neque@nisl.co.uk|9273
        Robin Randall|10108|faucibus.lectus.a@nonarcu.net|4232
        Stacey L. Kirby|Y4B 8Z5|euismod.enim@mauris.org|4200
        Joan Pearson|1867VB|convallis.erat@accumsannequeet.net|5002
        Herman Lambert|09774|vitae.velit.egestas@tinciduntaliquamarcu.com|1220
        Quentin Blankenship|48315-746|augue@consequat.edu|3387

2-1-f) Utilizae el comando echo -n 'contenido-archivo' | md5 sum  para crear un hash para validar los datos en el archivo
NEclients.txt

        cisco@labvm:~$ echo -n 'Name|Zip Code|Email|Pin #
        > 
        > Hannah Caldwell|7624|nec@ligula.net|6111
        > Rhiannon B. Langley|46872|fermentum@cursusnon.co.uk|9781
        > Nigel Ward|3584|convallis.erat.eget@luctusvulputatenisi.org|4896
        > Alvin Farley|69508|lectus@volutpat.co.uk|5358
        > Clark U. Pratt|23441|tincidunt.neque@nisl.co.uk|9273
        > Robin Randall|10108|faucibus.lectus.a@nonarcu.net|4232
        > Stacey L. Kirby|Y4B 8Z5|euismod.enim@mauris.org|4200
        > Joan Pearson|1867VB|convallis.erat@accumsannequeet.net|5002
        > Herman Lambert|09774|vitae.velit.egestas@tinciduntaliquamarcu.com|1220
        > Quentin Blankenship|48315-746|augue@consequat.edu|3387' | md5sum
        4dff78485308281b339bfda9236eda45  -

2-1-g) ¿Los dos valores hash para NEclients.txt son iguales?

        FileName | NEclients.txt | Hash| 4dff78485308281b339bfda9236eda45
        
        4dff78485308281b339bfda9236eda45
        
        Ambos Hash coinciden

2-1-f) El archivo que ha sido manipulado y tiene un hash incorrecto es :

    I)        
        NWclients.txt

        Name|Zip Code|Email|Pin #
        
        Stuart M. Barnes|3930|aliquam.iaculis.lacus@nec.ca|6893
        Tanya X. Sharp|5990|risus@ornare.co.uk|9285
        Cheyenne Garza|1493|Quisque.porttitor.eros@nec.com|2664
        Dolan Yates|7991WA|est@Fuscediamnunc.org|3437
        Hiroko Fleming|394867|Integer.in.magna@ac.co.uk|1880
        Brennan Whitney|10539|consectetuer.adipiscing.elit@Pellentesque.net|8600
        Kylan Z. Armstrong|53563-945|aliquam.iaculis.lacus@fringillaornareplacerat.ca|8698
        Peter G. Molina|26924|diam.dictum.sapien@sem.ca|3340
        Deborah Sanders|36376|ac@rutrum.net|9711
        Brett Travis|23-060|imperdiet.erat@Nuncsed.ca|2883
        
        
        cisco@labvm:~$ echo -n 'Name|Zip Code|Email|Pin #
        > 
        > Stuart M. Barnes|3930|aliquam.iaculis.lacus@nec.ca|6893
        > Tanya X. Sharp|5990|risus@ornare.co.uk|9285
        > Cheyenne Garza|1493|Quisque.porttitor.eros@nec.com|2664
        > Dolan Yates|7991WA|est@Fuscediamnunc.org|3437
        > Hiroko Fleming|394867|Integer.in.magna@ac.co.uk|1880
        > Brennan Whitney|10539|consectetuer.adipiscing.elit@Pellentesque.net|8600
        > Kylan Z. Armstrong|53563-945|aliquam.iaculis.lacus@fringillaornareplacerat.ca|8698
        > Peter G. Molina|26924|diam.dictum.sapien@sem.ca|3340
        > Deborah Sanders|36376|ac@rutrum.net|9711
        > Brett Travis|23-060|imperdiet.erat@Nuncsed.ca|2883' | md5sum
        13d2c0f0d00fcc3dc4d703f9694089f5  -
        
        FileName | NWclients.txt | Hash| 2c77ff70d5f7a2a720d231617157faa4
        
        NO COINCIDEN

    II)
        FileName | Nclients.txt | Hash| 8040e56207aab9dd331566b79dca37dd
        
        Name|Email|Company|Zip Code
        
        Grant K. Dyer|mattis.semper.dui@luctusut.edu|Est Foundation|I9Z 9AZ
        Tamekah O. Petty|odio.Phasellus.at@magnatellusfaucibus.co.uk|Posuere Cubilia Limited|45-937
        Adam H. Buck|sagittis@enim.edu|Pede Blandit Congue Company|647129
        Calvin V. Hays|elit.a@vitaedolor.net|Nunc Nulla Vulputate LLP|00078
        Zane Casey|luctus@mauris.com|Iaculis Incorporated|72240
        Rudyard W. Dalton|lorem@Nuncullamcorpervelit.co.uk|Auctor Nunc PC|626714
        Lamar Q. Allen|aliquet@sagittisNullamvitae.org|Et Rutrum Corp.|44736
        Michelle Sloan|dolor.sit.amet@seddictum.edu|Nisi PC|00312
        Haley E. Bass|nec@eu.com|Lorem Associates|00079
        Larissa G. Swanson|vulputate@diamnuncullamcorper.com|Ut Limited|0626QT
        
        cisco@labvm:~$ echo -n 'Name|Email|Company|Zip Code
        > 
        > Grant K. Dyer|mattis.semper.dui@luctusut.edu|Est Foundation|I9Z 9AZ
        > Tamekah O. Petty|odio.Phasellus.at@magnatellusfaucibus.co.uk|Posuere Cubilia Limited|45-937
        > Adam H. Buck|sagittis@enim.edu|Pede Blandit Congue Company|647129
        > Calvin V. Hays|elit.a@vitaedolor.net|Nunc Nulla Vulputate LLP|00078
        > Zane Casey|luctus@mauris.com|Iaculis Incorporated|72240
        > Rudyard W. Dalton|lorem@Nuncullamcorpervelit.co.uk|Auctor Nunc PC|626714
        > Lamar Q. Allen|aliquet@sagittisNullamvitae.org|Et Rutrum Corp.|44736
        > Michelle Sloan|dolor.sit.amet@seddictum.edu|Nisi PC|00312
        > Haley E. Bass|nec@eu.com|Lorem Associates|00079
        > Larissa G. Swanson|vulputate@diamnuncullamcorper.com|Ut Limited|0626QT' | md5sum
        b65a3767afe4db203a52c8a50f87f434  -
        
        NO COINCIDEN
    
    III)
        FileName | SEclients.txt | Hash| 520eb6c72cc2574decb731bc6230e223
        
        Name|Zip Code|Email|Pin #
        
        Germane Rutledge|60600|id.ante@etrutrum.ca|4782
        Alyssa Chandler|4001ZA|bibendum.sed.est@ultricesaauctor.org|3118
        Erica Burt|76167|laoreet.posuere@ut.edu|6627
        Iona Norton|69003|elit.pharetra.ut@aliquamiaculis.com|2558
        Joel Mcmahon|27979|iaculis.nec@nuncac.edu|9863
        Ira Raymond|70129-554|eget.odio.Aliquam@in.com|9881
        Ivory Acevedo|59-454|vitae.sodales.at@Donectempor.org|1843
        Willa X. Bridges|399542|nascetur.ridiculus.mus@lobortismaurisSuspendisse.com|7776
        Kimberly Garcia|37334|imperdiet.ornare@magna.org|1239
        Ethan Thornton|49438|penatibus@egetdictumplacerat.net|8090
        
        cisco@labvm:~$ echo -n 'Name|Zip Code|Email|Pin #
        > 
        > Germane Rutledge|60600|id.ante@etrutrum.ca|4782
        > Alyssa Chandler|4001ZA|bibendum.sed.est@ultricesaauctor.org|3118
        > Erica Burt|76167|laoreet.posuere@ut.edu|6627
        > Iona Norton|69003|elit.pharetra.ut@aliquamiaculis.com|2558
        > Joel Mcmahon|27979|iaculis.nec@nuncac.edu|9863
        > Ira Raymond|70129-554|eget.odio.Aliquam@in.com|9881
        > Ivory Acevedo|59-454|vitae.sodales.at@Donectempor.org|1843
        > Willa X. Bridges|399542|nascetur.ridiculus.mus@lobortismaurisSuspendisse.com|7776
        > Kimberly Garcia|37334|imperdiet.ornare@magna.org|1239
        > Ethan Thornton|49438|penatibus@egetdictumplacerat.net|8090' | md5sum
        9f322750d74bab2e5c493d13e68598e0  -
        
        NO COINCIDEN  

2-3) Escalar el ciberataque a la supervisora de Mike, Sally.  Ingresar "ftp hq.corp" para conectarse al servidor FTP 
de HQ, luego descargar los archivos que resultaron haber sido manipulado.

        C:\>ftp hq.corp
        Trying to connect...hq.corp
        Connected to hq.corp
        220- Welcome to PT Ftp server
        Username:sally
        331- Username ok, need password
        Password:
        230- Logged in
        (passive mode On)
        ftp>dir
        
        Listing /ftp directory from hq.corp: 
        0   : NEclients.txt                                      582
        1   : NWclients.txt                                      583
        2   : Nclients.txt                                       698
        3   : SEclients.txt                                      597
        4   : SWclients.txt                                      649
        5   : Sclients.txt                                       780
        
        ftp>get NWclients.txt
        
        Reading file NWclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 583 bytes]
        
        583 bytes copied in 0.042 secs (13880 bytes/sec)
        ftp>get Nclients.txt
        
        Reading file Nclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 698 bytes]
        
        698 bytes copied in 0.031 secs (22516 bytes/sec)
        ftp>get SEclients.txt
        
        Reading file SEclients.txt from hq.corp: 
        File transfer in progress...
        
        [Transfer complete - 597 bytes]
        
        597 bytes copied in 0.065 secs (9184 bytes/sec)
        ftp>quit
        
        221- Service closing control connection.
        C:\>

2-3-f) Verificar que los archivos manipulados esten ahora en HQ-Laptop-1 para que Sally lo analice en el futuro.

        C:\>dir
         
         Volume in drive C has no label.
         Volume Serial Number is 5E12-4AF3
         Directory of C:\
        
        12/31/1969  21:0 PM            583       NWclients.txt       
        12/31/1969  21:0 PM            698       Nclients.txt        
        12/31/1969  21:0 PM            597       SEclients.txt       
                        1878 bytes          3 File(s)   

3-b) Verificar que el archivo income.txt, este en la PC de Bob. Abrirlo y cipiar su contenido

        INCOME 
        2016
        2015
        $
        $
        Subscriptions
        4200
        3150
        Advertising
        11000
        7000
        Donations
        2000
        5500
        Entry fees from annual show
        1000
        1000
        General fundraising
        4000
        4300
        Interest
        1000
        2000
        Total income 
        22,000
        22,450

3-h) Usar el siguiente comando para crear un HMAC para el archivo income.txt. La clave secreta es cisco123.


        cisco@labvm:~$ openssl dgst -sha256 -hmac cisco123 income.txt 
        HMAC-SHA256(income.txt)= b138706cb55787d2a01934b224edad32203f87470ff6c7ffb9bd126786d1830d

¿Por qué el uso de HMAC es más seguro que el hashing general?
Para producir un hash específico, necesita tanto el mensaje original como una clave secreta.