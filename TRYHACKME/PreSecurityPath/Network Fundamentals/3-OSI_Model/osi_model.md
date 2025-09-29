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

# 1.5 Couche Session 

Une fois que les données ont été correctement traduites ou formatées par la couche de présentation (couche 6), la couche de session (couche 5) commence à créer et à maintenir la connexion avec l’autre ordinateur auquel les données sont destinées. Lorsqu’une connexion est établie, une session est créée. Tant que cette connexion reste active, la session l’est également.

La couche de session est aussi responsable de fermer la connexion lorsqu’elle n’a pas été utilisée pendant un certain temps ou si elle est perdue.
De plus, une session peut contenir des points de contrôle (“checkpoints”) qui permettent, en cas de perte de données, de ne renvoyer que les parties les plus récentes. Cela permet d’économiser de la bande passante.

Il est important de noter que les sessions sont uniques — ce qui signifie que les données ne peuvent pas circuler entre différentes sessions, mais uniquement à l’intérieur de la session à laquelle elles appartiennent.

# 1.6 Couche Présentation

La couche 6 appelée couche de présentation, est celle où la standardisation commence à se mettre en place. 
En effet, même si les développeurs peuvent créer différents logiciels 
— par exemple des clients de messagerie distincts — 
les données doivent tout de même être traitées de la même manière, quel que soit le fonctionnement du logiciel.

Cette couche agit comme un traducteur des données vers et depuis la couche application (couche 7).
L’ordinateur récepteur doit être capable de comprendre les données envoyées par un autre ordinateur, même si elles ont été produites dans un format différent. 
Par exemple, lorsque vous envoyez un e-mail, le destinataire peut utiliser un autre client de messagerie que le vôtre, mais le contenu du message doit tout de même s’afficher de la même façon.

Des mécanismes de sécurité, tels que le chiffrement des données (comme le protocole HTTPS lors de la visite d’un site sécurisé), sont également mis en œuvre à ce niveau.

# 1.7 Couche Application
C’est à ce niveau que se trouvent les protocoles et les règles déterminant la manière dont l’utilisateur interagit avec les données envoyées ou reçues.

Les applications courantes telles que les clients de messagerie, les navigateurs web, ou les logiciels de transfert de fichiers comme FileZilla offrent une interface graphique conviviale (GUI)
permettant aux utilisateurs d’interagir facilement avec les données transmises ou reçues.

Parmi les autres protocoles utilisés à cette couche, on trouve le DNS (Domain Name System), qui permet de traduire les adresses de sites web en adresses IP.