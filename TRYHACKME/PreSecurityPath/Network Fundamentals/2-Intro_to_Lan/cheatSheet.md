LAN = Local Area Network

Topologie en Bus
Topologie en Etoile
Topologie en Anneau

Switch = commutateur réseau qui connecte plusieurs appareils et redirige les données uniquement vers la machine concernée (plus intelligent qu’un hub).
Hub = concentrateur réseau qui connecte plusieurs appareils et diffuse les données à toutes les machines connectées (moins efficace).
Router = Appareil qui connecte différents réseaux entre eux. (Internet à ton pc, Internet à un LAN, ou un LAN à un autre LAN.)

IP = Adresse de 4 octets.
masque de sous réseau contient 32 bits et va de 0 à 255 et peut être utilisé de 3 différentes façon :
- Adresse Réseaux = Identifier le début du réseau et attester de son existence. (192.168.1.0)
- Adresse Hôte = Identifier un appareil dans le sous-réseau. (192.168.1.100)
- Passerelle par défault = Adresse spéciale assignée à un appareil capable d’envoyer des données vers un autre réseau. (192.168.1.254)

ARP = Address Resolution Protocol (protocole de résolution d’adresses) (utilisé pour trouver a qui envoyé les données)
Deux différents packets : 
- ARP Request (requête ARP) = Quelle est l’adresse MAC qui correspond à cette adresse IP ?
- ARP Reply (réponse ARP) = Adresse Mac renvoyé par le seul appareil correspondant à l'adresse IP.

DHCP = Dynamic Host Configuration Protocol = Serveur qui automatise l'adressage des adresses IP.
DHCP Discover = Requête d'un appareil lors de la connexion au réseaux pour vérifier la présence d'un serveur DHCP.
DHCP Offer = Réponse du DHCP avec une proposition d'une IP que l'appareil peut utiliser.
DHCP Request = Réponse de l'appareil comme quoi il veut utiliser l'adresse IP proposée.
DHCP ACK = confirmation final qui indique que le processus est terminé et que l'appareil peut commencer à utiliser l'adresse IP.