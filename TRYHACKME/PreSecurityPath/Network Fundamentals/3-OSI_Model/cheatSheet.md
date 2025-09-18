OSI (Open Systems Interconnection Model) = modèle fondamental définit comment les appareils d'un réseau vont envoyer, recevoir et interpréter les données.
Encapsulation = le processus de la traversé des 7 couches du model OSI.

Carte réseau = possède l'adresse MAC

7 couches :
- 1.Physique
    Tous les composants matériel (exemple : câble ethernet).
- 2.Liaison de données
    Reçoit un paquet de la couche réseau qui contient l'adresse IP de l'appareil distant, et y ajoute l'adresse MAC du destinataire.
    Présente également les données dans le format adapté à la transmission.
- 3.Réseaux
    Determine le chemin le plus optimal pour envoyé les paquets données.
    A cette couche tout ce fait via adresse IP.
    Deux protocoles utilisés : 
    - OSPF (Open Shortest Path First)
    - RIP (Routing Information Protocol).
- 4.Transport 
    - TCP (Transmission Control Protocol) (Partage de fichier, Navigation Internet, envoie de mails car nous avons besoin de données exactes et complètes)
        - Garantit l'exactitude des données mais necessite une connexion fiable.
        - la vitesse de transmission est faite par rapport a l'appareil recepteur (peut donc etre lent).
        - Bcp de traitement pour assurer la fiabilité (plus lent qu'UDP).
    - UDP (User Datagram Protocol) (Protocole utilisé pour découverte d'appareil DHCP ou ARP, Streaming vidéo)
        - Envoie toute les données sans attendre de confirmation de reception (Plus rapide mais moins fiable)
        - Laisse la couche application (logiciel) si il y a une vitesse limitée. (Connexion instable => expérience Médiocre)
        