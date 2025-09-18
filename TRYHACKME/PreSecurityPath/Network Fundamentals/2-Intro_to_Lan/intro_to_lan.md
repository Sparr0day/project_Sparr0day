## 1 Introduction aux topologies LAN
Au fil des années, différentes conceptions de réseaux ont été expérimentées et mises en œuvre. En réseautique, lorsque l’on parle de “topologie”, on fait référence à la conception ou à l’agencement physique/logique du réseau. Voyons ci-dessous les avantages et inconvénients de certaines topologies courantes.

# 1.1 Topologie en étoile (Star Topology)
======================================
[==== Voir Image "topologie-etoile.png" ====]
======================================

Le principe de la topologie en étoile est que chaque appareil est connecté individuellement via un dispositif central comme un switch ou un hub. 
C’est la topologie la plus répandue aujourd’hui grâce à sa fiabilité et sa scalabilité, malgré son coût plus élevé.

Toute information envoyée à un appareil dans cette topologie transite par le dispositif central auquel il est connecté.

Avantages :

- Très scalable : il est facile d’ajouter de nouveaux appareils à mesure que le réseau grandit.
- Plus fiable qu’une topologie plus simple, car les défaillances locales n’affectent pas l’ensemble du réseau.

Inconvénients :

- Plus coûteuse en câbles et matériel réseau dédié.
- Maintenance plus complexe à mesure que le réseau s’agrandit, ce qui peut compliquer le dépannage.
- Point central unique : si le dispositif central tombe en panne, les appareils connectés ne peuvent plus envoyer ni recevoir de données. Heureusement, ces équipements centraux sont souvent robustes.

# 1.2 Topologie en bus (Bus Topology)
======================================
[==== Voir Image "topologie-bus.png" ====]
=====================================

Le principe de la topologie en bus est que tous les appareils sont connectés à un câble unique, appelé backbone, qui sert de canal de communication principal. Chaque appareil peut envoyer et recevoir des données via ce câble commun.

Toute information transite par le même câble, ce qui rend la gestion simple mais peut créer des ralentissements si plusieurs appareils communiquent simultanément.

Avantages :

- Simple à mettre en place et coût réduit en câbles et matériel réseau.
- Facile à étendre pour un petit nombre d’appareils.

Inconvénients :

- Si le câble principal est endommagé, tout le réseau s’arrête.
- Performances limitées : les données passent par le même câble, ce qui peut créer des bouchons lorsque plusieurs appareils envoient des informations en même temps.
- Peu de redondance : aucune alternative n’existe si le câble principal tombe en panne.

# 1.3 Topologie en anneau (Ring Topology)
======================================
[==== Voir Image "topologie-anneau.png" ====]
======================================

Le principe de la topologie en anneau est que chaque appareil est connecté directement à deux autres appareils pour former une boucle. Les données circulent autour de cette boucle jusqu’à atteindre l’appareil destinataire. 

Chaque appareil peut transmettre les données reçues uniquement lorsqu’il n’a pas de données à envoyer lui-même.
Cette topologie nécessite moins de câbles et moins de matériel dédié qu’une topologie en étoile, car il n’y a pas de dispositif central.

Avantages :

- Réduction des bouchons de données, car le trafic est organisé et limité à la boucle.
- Facilité de dépannage, car les données circulent dans une direction unique et les problèmes peuvent être localisés rapidement.
- Moins coûteuse en matériel qu’une topologie en étoile.

Inconvénients :

- Point de défaillance unique : si un câble ou un appareil tombe en panne, l’ensemble du réseau s’arrête.
- Transmission moins efficace : les données peuvent devoir passer par plusieurs appareils avant d’atteindre leur destination.
- Scalabilité limitée : ajouter ou retirer un appareil peut interrompre temporairement la communication.

# 1.4 Qu'est-ce qu'un Switch ?
======================================
[==== Voir Image "switch.png" ====]
======================================
Les switches sont des dispositifs dédiés au sein d’un réseau, conçus pour regrouper plusieurs autres appareils tels que des ordinateurs, des imprimantes ou tout autre périphérique compatible réseau utilisant l’Ethernet. Ces différents appareils se connectent aux ports d’un switch.

Les switches se trouvent généralement dans des réseaux de grande taille, comme dans les entreprises, les écoles ou des réseaux d’une taille similaire. Un switch peut connecter un grand nombre d’appareils grâce à ses ports, qui peuvent être au nombre de 4, 8, 16, 24, 32 ou 64, selon le modèle.

Les switches sont plus efficaces que leurs équivalents (hubs/répéteurs). Ils gardent une trace des appareils connectés à chaque port. Ainsi, lorsqu’ils reçoivent un paquet de données, au lieu de le répéter à tous les ports comme le ferait un hub, ils l’envoient uniquement à la cible prévue, réduisant ainsi le trafic réseau.

# 1.5 Router ou Switch ?
Les switches et les routeurs peuvent être connectés entre eux.

La possibilité de le faire augmente la redondance (la fiabilité) d’un réseau en ajoutant plusieurs chemins pour le passage des données. Si un chemin tombe en panne, un autre peut être utilisé.

Bien que cela puisse réduire les performances globales du réseau, car les paquets doivent parfois emprunter un chemin plus long, il n’y a aucune interruption de service — un petit prix à payer par rapport à l’alternative.

# 1.6 Qu'est-ce qu'un Router ?
======================================
[==== Voir Image "router.png" ====]
======================================

C’est le rôle d’un routeur de connecter des réseaux et de faire circuler les données entre eux. Il accomplit cela grâce au routage (d’où son nom : router/routeur).

Le routage (routing) désigne le processus par lequel les données voyagent à travers les réseaux. Il consiste à créer un chemin entre les réseaux afin que les données puissent être correctement transmises.

Le routing est particulièrement utile lorsque les appareils sont connectés par plusieurs chemins, comme dans l’exemple du schéma ci-dessous.

## 2 Introduction au subnetting (sous‑réseautage)
Les réseaux existent sous toutes les formes et tailles.
Le subnetting désigne le processus de division d’un réseau en sous-réseaux.

Prenons l’exemple d’une entreprise ; elle possède différents départements tels que :
- Comptabilité
- Finance
- Ressources Humaines

======================================
[==== Voir Image "company-network.png" ====]
======================================

De la même manière que tu sais à qui envoyer une information dans le bon département dans la vie réelle, les réseaux doivent aussi le savoir.

Les administrateurs réseau utilisent le subnetting pour catégoriser et attribuer des parties spécifiques d’un réseau afin de refléter cette organisation.

Le subnetting est réalisé en divisant le nombre d’hôtes pouvant exister dans un réseau, ce qui est représenté par un nombre appelé : masque de sous-réseau (subnet mask).
Revenons à notre schéma d'une adresse ip :
======================================
[==== Voir Image "IP-Adress.png" ====]
======================================
Une adresse IP est composée de quatre sections appelées octets. 
Il en va de même pour un masque de sous-réseau, qui est également représenté par un nombre de quatre octets (32 bits), allant de 0 à 255.

Les sous-réseaux utilisent les adresses IP de trois manières différentes :

- Identifier l’adresse du réseau
- Identifier l’adresse de l’hôte
- Identifier la passerelle par défaut

Décomposons ces trois usages dans le tableau ci-dessous :
----------------------------------------------------------------------------------------------------------
Type	          | Objectif	                |  Explication	                    |  Exemple
----------------------------------------------------------------------------------------------------------
Adresse de réseau |	Identifier le début du      |  Par exemple, un appareil         |  192.168.1.0.
                  | réseau et attester de son   |  avec l’adresse IP 192.168.1.100  |
                  | existence.	                |  appartient au réseau             |             
                  |                             |  identifié par 192.168.1.0.       |
----------------------------------------------------------------------------------------------------------
Adresse d’hôte    | Identifier un appareil      |  Par exemple, un appareil aura    |  192.168.1.100
                  | dans le sous-réseau.        |  une adresse telle                |
                  |                             |  que 192.168.1.100.               |
----------------------------------------------------------------------------------------------------------
Passerelle par    | Adresse spéciale assignée   | Toute donnée destinée à un        | 192.168.1.254
défault           | à un appareil capable       | appareil qui n’est pas dans le    |
                  | d’envoyer des données vers  | même réseau                       |
                  | un autre réseau.            | (ex. pas dans 192.168.1.0)        |
                  |                             | sera envoyée à cet appareil.      |
                  |                             | La passerelle utilise généralement| 
                  |                             | la première ou la dernière adresse|
                  |                             | hôte d’un réseau (.1 ou .254).    |     
----------------------------------------------------------------------------------------------------------    
Dans les petits réseaux, comme à la maison, vous êtes sur un seul sous-réseau, car il est peu probable que vous ayez besoin de connecter plus de 254 appareils en même temps.

En revanche, dans des environnements comme les entreprises, on trouve beaucoup plus d’appareils (PC, imprimantes, caméras, capteurs), ce qui rend le subnetting nécessaire.

Le subnetting apporte plusieurs avantages, notamment :
- Efficacité
- Sécurité
- Contrôle total

Nous verrons plus tard en détail les différents bénéfices. Pour l’instant, concentrons-nous sur la partie sécurité.

Prenons l’exemple d’un café :
- Un réseau pour les employés, caisses et autres appareils internes
- Un réseau pour le public (Wi-Fi)

Le subnetting permet de séparer ces deux usages, tout en bénéficiant d’une connexion au réseau global (Internet).

## 3 ARP 
Les appareils peuvent avoir deux identifiants : 
- une adresse MAC.
- une adresse IP. 
Le protocole de résolution d’adresses (Address Resolution Protocol, ou ARP) est la technologie responsable de permettre aux appareils de s’identifier sur un réseau.

En simple, ARP permet à un appareil d’associer son adresse MAC à une adresse IP sur le réseau. 
Chaque appareil conserve un journal des adresses MAC associées aux autres appareils.

Quand un appareil souhaite communiquer avec un autre, il envoie une diffusion (broadcast) à tout le réseau pour rechercher l’appareil en question. Grâce à ARP, il peut trouver l’adresse MAC (donc l’identifiant physique) de l’appareil afin d’établir la communication.

Comment fonctionne ARP ?
Chaque appareil d’un réseau possède un registre pour stocker des informations, appelé un cache. Dans le contexte d’ARP, ce cache conserve les associations IP/MAC des autres appareils présents sur le réseau.

Pour associer ces deux identifiants (adresse IP et adresse MAC), ARP utilise deux types de messages :
- ARP Request (requête ARP)
- ARP Reply (réponse ARP)

Lorsqu’une requête ARP est envoyée, un message est diffusé sur le réseau pour demander :
    - « Quelle est l’adresse MAC qui correspond à cette adresse IP ? »
Quand les autres appareils reçoivent ce message, seul celui qui possède cette adresse IP répond en envoyant une réponse ARP avec son adresse MAC.
L’appareil demandeur peut alors mémoriser cette association et la stocker dans son cache ARP pour une future utilisation.

Ce processus est illustré dans le schéma ci-dessous :
======================================
[==== Voir Image "ARP.png" ====]
======================================     

## 4 DHCP
Les adresses IP peuvent être attribuées soit manuellement, en les entrant directement dans un appareil, soit automatiquement (et le plus souvent) grâce à un serveur DHCP (Dynamic Host Configuration Protocol).

Lorsqu’un appareil se connecte à un réseau et qu’aucune adresse IP ne lui a été assignée manuellement, il envoie une requête (DHCP Discover) pour vérifier si des serveurs DHCP sont présents sur le réseau.

Le serveur DHCP répond alors avec une proposition d’adresse IP que l’appareil peut utiliser (DHCP Offer). L’appareil envoie ensuite une réponse confirmant qu’il veut utiliser l’adresse proposée (DHCP Request). Enfin, le serveur DHCP envoie une confirmation finale indiquant que le processus est terminé et que l’appareil peut commencer à utiliser l’adresse IP (DHCP ACK).

======================================
[==== Voir Image "DHCP.png" ====]
======================================     