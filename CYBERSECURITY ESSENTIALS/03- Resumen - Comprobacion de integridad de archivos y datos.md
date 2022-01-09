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
