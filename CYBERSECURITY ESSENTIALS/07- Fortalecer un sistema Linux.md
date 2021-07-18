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


## 2) Ejecutar la herramienta Lynis:

a) Use el comando sudo ./lynis --auditor cisco para ejecutar Lynis. Esto me dio resultados para una variedad de 
funciones del sistema, comenzando con Arranque y servicios y terminando con endurecimiento, pruebas personalizadas y 
complementos.

    cisco@labvm:~/Downloads/lynis$ sudo ./lynis --auditor cisco

    [ Lynis 3.0.3 ]

    ################################################################################
    Lynis comes with ABSOLUTELY NO WARRANTY. This is free software, and you are
    welcome to redistribute it under the terms of the GNU General Public License.
    See the LICENSE file for details about using this software.

    2007-2021, CISOfy - https://cisofy.com/lynis/
    Enterprise support available (compliance, plugins, interface and tools)
    ################################################################################


    [+] Initializing program
    ------------------------------------
    - Detecting OS...                                           [ DONE ]
    - Checking profiles...                                      [ DONE ]

    ---------------------------------------------------
    Program version:           3.0.3
    Operating system:          Linux
    Operating system name:     Ubuntu
    Operating system version:  20.04
    Kernel version:            5.4.0
    Hardware platform:         x86_64
    Hostname:                  labvm
    ---------------------------------------------------
    Profiles:                  /home/cisco/Downloads/lynis/default.prf
    Log file:                  /var/log/lynis.log
    Report file:               /var/log/lynis-report.dat
    Report version:            1.0
    Plugin directory:          ./plugins
    ---------------------------------------------------
    Auditor:                   cisco
    Language:                  en
    Test category:             all
    Test group:                all
    ---------------------------------------------------
    - Program update status...                                  [ UPDATE AVAILABLE ]

      ===============================================================================
        Lynis update available
      ===============================================================================

        Current version is more than 4 months old

        Current version : 303   Latest version : 307

        Please update to the latest version.
        New releases include additional features, bug fixes, tests, and baselines.

        Download the latest version:

        Packages (DEB/RPM) -  https://packages.cisofy.com
        Website (TAR)      -  https://cisofy.com/downloads/
        GitHub (source)    -  https://github.com/CISOfy/lynis

      ===============================================================================

    [+] Initializing program
    ------------------------------------
     - Detecting OS... [ DONE ]
       - Checking profiles... [ DONE ]

    <omiti salidas para facilitar el practico>

    [+] Boot and services
    ------------------------------------
     - Service Manager [ systemd ]
       - Checking UEFI boot [ DISABLED ]
       - Checking presence GRUB2 [ FOUND ]

    <omiti salidas para facilitar el practico>

    [+] Hardening
    ------------------------------------
     - Installed compiler(s) [ FOUND ]
     - Installed malware scanner [ NOT FOUND ]
     - Non-native binary formats [ NOT FOUND ]
    [+] Custom tests
    ------------------------------------
     - Running custom tests... [ NONE ]
    [+] Plugins (phase 2)
    ------------------------------------

b) La siguiente sección son los resultados de Lynis 3.0.3. En los resultados incluyen advertencias (que se muestran a 
continuación). También habrá una sección con una lista de Sugerencias, que enumerará, en este caso 52.


