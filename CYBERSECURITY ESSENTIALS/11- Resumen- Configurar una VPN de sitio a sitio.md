## Parte 2: Crear una VPN site-to-site:

1-b) En el router BRouter1,  ingrese con la clave BRsecurity

    Authorized Access Only!

    User Access Verification

    Password: BRsecurity

    Branch>


1-c) Use el comando enable para configurar una contraseña: BRc1sco0@!

    Branch>enable
    Password: 
    Branch#

1-d) Entre en la configuración global:

    Branch# configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    Branch(config)#

1-e-a) Configuré una política ISAKMP con una prioridad de 10, cifrado AES de 256 bits, clave de autenticación 
precompartida, D-H grupo 5 y una vida útil de 900 segundos.

    Branch(config)#crypto isakmp policy 10
    Branch(config-isakmp)#encr aes 256
    Branch(config-isakmp)#authentication pre-share
    Branch(config-isakmp)#group 5
    Branch(config-isakmp)#lifetime 900
    Branch(config-isakmp)#exit

1-e-b) Configuré cisco123 como la clave precompartida e identifique la dirección IP del enrutador HQ-Edge del extremo 
remoto.

    Branch(config)#crypto isakmp key cisco123 address 10.0.0.50

1-e-c) Creé un conjunto de transformación IPsec que se utilice en las negociaciones de la asociación de seguridad (SA)

    Branch(config)#crypto ipsec transform-set Branch-HQ esp-aes esp-sha-hmac

1-e-d)  Creé un mapa criptográfico que asocie el tráfico que coincide con una lista de acceso a un par y varias 
configuraciones de IKE e IPsec

    Branch(config)#crypto map CMAP 10 ipsec-isakmp
    % NOTE: This new crypto map will remain disabled until a peer
            and a valid access list have been configured.
    Branch(config-crypto-map)#set peer 10.0.0.50
    Branch(config-crypto-map)#set pfs group5
    Branch(config-crypto-map)#set security-association lifetime seconds 1800
    Branch(config-crypto-map)#set transform-set Branch-HQ
    Branch(config-crypto-map)#match address 101
    Branch(config-crypto-map)#exit

2-a) Asocié el mapa criptográfico a la interfaz del enrutador. Aplique el mapa criptográfico a la interfaz G0/0/0 en 
BRouter1. Esto identifica el punto final del túnel.

    Branch(config)#interface g0/0/0
    Branch(config-if)#crypto map CMAP
    *Jan  3 07:16:26.785: %CRYPTO-6-ISAKMP_ON_OFF: ISAKMP is ON
    Branch(config-if)#



