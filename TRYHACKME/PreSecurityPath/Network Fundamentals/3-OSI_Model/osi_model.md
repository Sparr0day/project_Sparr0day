## 1 What is the OSI Model ? 
Le modèle OSI (Open Systems Interconnection Model) est un modèle essentiel utilisé en réseau. 
Ce modèle fondamental définit la manière dont tous les appareils connectés à un réseau vont envoyer, recevoir et interpréter les données.

L’un des principaux avantages du modèle OSI est que les appareils peuvent avoir des fonctions et des conceptions différentes dans un réseau tout en communiquant entre eux.
Les données envoyées à travers un réseau qui suit l’uniformité du modèle OSI peuvent être comprises par d’autres appareils.

Le modèle OSI est constitué de sept couches, illustrées dans le schéma ci-dessous. Chaque couche a un ensemble de responsabilités spécifiques et elles sont organisées de la couche 7 jusqu’à la couche 1.

À chaque couche que traversent les données, des processus spécifiques ont lieu et des informations supplémentaires sont ajoutées à ces données. 

Pour l’instant, il suffit de comprendre que ce processus s’appelle l’encapsulation, et de voir à quoi ressemble le modèle OSI dans ce schéma :
======================================
[==== Voir Image "topologie-bus.png" ====]
=====================================

# 1.1 Couche Physique (Physical).
Elle concerne les composants matériels physiques utilisés dans le réseau et constitue la couche la plus basse que l’on trouve. 

Par exemple, les câbles Ethernet :
======================================
[==== Voir Image "layer1_ethernet_cables.png" ====]
=====================================

# 1.2 Couche Liaison de données.
La couche liaison de données se concentre sur l’adressage physique de la transmission. 
Elle reçoit un paquet provenant de la couche réseau (qui contient l’adresse IP de l’ordinateur distant) et y ajoute l’adresse physique MAC (Media Access Control) du destinataire.

Lorsqu’une information est envoyée sur un réseau, c’est en réalité l’adresse physique qui est utilisée pour déterminer exactement où envoyer les données.

De plus, c’est également le rôle de la couche liaison de données de présenter les données dans un format adapté à la transmission.

# 1.3 Couche Réseau.
C'est là où se produit la magie du routage et de la réassemblage des données.

Le routage détermine simplement le chemin le plus optimal pour envoyer ces paquets de données.
Certains protocoles à cette couche déterminent exactement quel est le chemin "optimal" que les données doivent emprunter :
- OSPF (Open Shortest Path First)
- RIP (Routing Information Protocol).

Les facteurs qui déterminent le chemin choisi :

- Quel chemin est le plus court ? 
    le chemin traversant le moins d’appareils.
- Quel chemin est le plus fiable ? 
    y a-t-il eu des pertes de paquets sur ce chemin auparavant ?
- Quel chemin a la connexion physique la plus rapide ? 
    Par exemple, une connexion cuivre (plus lente) ou fibre ?

À cette couche, tout se fait via les adresses IP comme 192.168.1.100.
Les appareils capables de livrer des paquets en utilisant des adresses IP sont appelés appareils de couche 3, car ils travaillent à la troisième couche du modèle OSI.
=====================================
[==== Voir Image "network.png" ====]
=====================================

# 1.4 Couche Transport
Lorsque des données sont envoyées entre des appareils, elles suivent l’un des deux protocoles différents :
- TCP
- UDP

Le Transmission Control Protocol (TCP) est conçu pour la fiabilité et la garantie de livraison.
Il réserve une connexion constante entre les deux appareils pendant toute la durée nécessaire à l’envoi et à la réception des données.

De plus, TCP intègre un contrôle d’erreurs dans sa conception. 
Ce contrôle d’erreurs permet à TCP de garantir que les données envoyées depuis les petits morceaux de la couche session (couche 5) sont reçues et réassemblées dans le bon ordre.

Voici un résumé des avantages et inconvénients de TCP :
-------------------------------------------------------------------------------------------------
Avantages de TCP                    |   Inconvénients de TCP
-------------------------------------------------------------------------------------------------
Garantit l’exactitude des données.	|   Nécessite une connexion fiable entre les deux appareils. 
                                    |   Si un petit morceau de données n’est pas reçu, 
                                    |   l’ensemble du paquet ne peut pas être utilisé.
-------------------------------------------------------------------------------------------------
Capable de synchroniser deux        |   Une connexion lente peut ralentir l’autre appareil, 
appareils pour éviter qu’ils soient |   car la connexion reste réservée sur l’appareil récepteur.
saturés de données.	                | 
-------------------------------------------------------------------------------------------------
Réalise beaucoup plus de traitements|   TCP est nettement plus lent que UDP car davantage de traitement
pour assurer la fiabilité.	        |   est effectué par les appareils utilisant ce protocole.
-------------------------------------------------------------------------------------------------
TCP est utilisé dans des situations telles que le partage de fichiers, la navigation sur Internet ou l’envoi d’emails, car ces services nécessitent que les données soient exactes et complètes (ce n’est pas pratique d’avoir un fichier à moitié reçu !).

Dans ce schéma, on peut voir comment une image de chat est découpée en petits paquets de données depuis le serveur web, puis comment l’ordinateur reconstitue l’image dans le bon ordre :
======================================
[==== Voir Image "TCP.png" ====]
======================================

User Datagram Protocol (ou UDP) n’est pas aussi avancé que son “frère” TCP. 
Il ne dispose pas des nombreuses fonctionnalités offertes par TCP, comme le contrôle d’erreurs et la fiabilité.

En fait, toutes les données envoyées via UDP le sont qu’elles arrivent ou non. Il n’y a aucune synchronisation entre les deux appareils ni garantie de livraison ; on croise juste les doigts et on espère que ça marche.

Bien que cela semble être un inconvénient, UDP possède ses avantages, que nous présentons dans le tableau ci-dessous :
-------------------------------------------------------------------------------------------------
Avantages de UDP                    |   Inconvénients de UDP
-------------------------------------------------------------------------------------------------
UDP est beaucoup plus 	            |   UDP ne garantit pas la réception des données. 
rapide que TCP.                     |   
                                    |   
-------------------------------------------------------------------------------------------------
UDP laisse la couche application    |   Cela signifie que les connexions instables entraînent  
(le logiciel utilisateur) décider   |   une expérience utilisateur médiocre.
s’il y a un contrôle sur la vitesse |
d’envoi des paquets.                | 
-------------------------------------------------------------------------------------------------
UDP est assez flexible pour les     |   UDP ne réserve pas une connexion continue sur un 
développeurs dans ce sens.	        |   appareil comme TCP
-------------------------------------------------------------------------------------------------
UDP est utile dans les situations où de petits morceaux de données sont envoyés.
Exemple :
- Les protocoles utilisés pour découvrir des appareils (comme ARP et DHCP [refto => Intro to LAN])
- Les fichiers volumineux comme le streaming vidéo (où il est acceptable que certaines parties de la vidéo soient pixélisées, car les pixels représentent simplement des données perdues !)

Sur ce schéma, on voit maintenant que seuls les paquets #1 et #3 ont été reçus par l’ordinateur, 
ce qui signifie que la moitié de l’image est manquante.
======================================
[==== Voir Image "UDP.png" ====]
=====================================