Topologie Globale

Le réseau présenté dans l'image montre une architecture simple comprenant:

    Un pare-feu FortiGate (version 7.0.9)

    Un commutateur IOU1 avec de nombreux ports Ethernet (e0/0 à e0/...)

    Un cloud représentant Internet (Cloud1) avec l'adresse IP 192.168.69.131

Connexions Principales

    FortiGate:

        Dispose de deux interfaces: Port1(Routage vers Internet) et Port2 (Gestion des VLANs)

        Connecté à Internet (Cloud1) via Port1 pour accéder à l'interface Web

        NAT et DHCP activé

    IOU1:

        Commutateur avec un très grand nombre de ports Ethernet (la liste semble tronquée)

        Connecté au FortiGate pour l'accès Internet et le routage inter-VLANs 

          e0/0 : mode trunk
          e0/1 : mode access lié au VLAN10
          e0/2 : mode access lié au VLAN20
          e0/3 : mode access lié au VLAN30

Configuration des VLANs

    La communication inter-VLAN est activée sur le réseau

    Tous les VLANs peuvent communiquer avec Cloud1 (Internet)

    Cela implique que:

        Le FortiGate fait office de routeur inter-VLAN

        Des règles de routage et de filtrage appropriées sont configurées pour permettre cette communication

        Le FortiGate sert également de passerelle par défaut pour tous les VLANs vers Internet et de serveur DHCP

    utiliser la commande "ip dhcp" sur les VPCs pour obtenir une adresse depuis le serveur DHCP
