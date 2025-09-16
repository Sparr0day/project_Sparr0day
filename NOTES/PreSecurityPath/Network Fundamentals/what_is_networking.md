## Introduction - What is Networking ? 
Les réseaux sont simplement des choses connectés entres elles.

On retrouve des réseaux partout dans la vie quotidienne : 

- Le systeme de transports en commun d'une ville.
- Infrastructures tel que le réseau électrique national.
- liens sociaux dans le voisinage.
- Et plus spécifiquement, dans l'informatique, c'est la même idée mais avec des appareiles technologiques. Par exemple : le téléphone d'aujourd'hui sert surtout à avoir accès à d'autres choses (Internet, app, appels ...).

Un réseau informatique peut être composé de 2 appareils seulement… jusqu’à plusieurs milliards.
Ces appareils peuvent être : ton ordinateur portable, ton téléphone, des caméras de sécurité, des feux de circulation, voire même du matériel agricole !

Les réseaux sont intégrés à notre vie de tous les jours :
- récolter des données météo,
- acheminer l’électricité,
- décider de la priorité sur une route, etc.

Comme les réseaux sont partout dans le monde moderne, comprendre leur fonctionnement est une notion essentielle en cybersécurité.

Enfin, les réseaux existent sous toutes sortes de formes et tailles, un sujet qui sera approfondi tout au long de ce module.

## 1 Qu'est-ce qu'internet ? 
Maintenant que nous avons vu ce qu’est un réseau et comment il est défini en informatique (des appareils connectés entre eux), voyons ce qu’est Internet.

L’Internet, c’est un immense réseau, composé d’une multitude de petits réseaux connectés entre eux.

En prenant un exemple :

Alice se fait de nouveaux amis, Zayn et Toby, et veut les présenter à Bob et Jim.
Le problème : Alice est la seule à parler la même langue que Zayn et Toby.
Résultat : Alice joue le rôle de messager et permet à tout le monde de communiquer.

💡 Grâce à Alice, un nouveau réseau se forme.

# 1.1 Un peu d’histoire

La première version d’Internet remonte au projet ARPANET, à la fin des années 1960.
→ Financé par le Département de la Défense des États-Unis, c’était le premier réseau documenté en fonctionnement.
Mais ce n’est qu’en 1989 que l’Internet tel qu’on le connaît est né, grâce à Tim Berners-Lee qui inventa le World Wide Web (WWW).

À partir de ce moment-là, Internet est devenu un espace pour stocker et partager des informations, comme aujourd’hui.

# 1.2 Internet, en pratique

Si on compare avec l’exemple d’Alice et ses amis :
L’Internet ressemble à une version géante de ce type de schéma, où des petits réseaux s’unissent pour en former un plus grand.

Ces petits réseaux sont appelés réseaux privés.

Quand plusieurs de ces petits réseaux sont connectés ensemble, ils forment un réseau public → Internet.

Pour résumer :
- Un réseau privé = un petit réseau isolé,
- Un réseau public = l’ensemble des petits réseaux connectés entre eux = Internet.

Les appareils qui se connectent à un réseau utilisent des étiquettes (identifiants) pour se reconnaître et communiquer.

## 2 Savoir identifier les appareils sur un Réseau
Pour identifier des appareils, il y a deux moyens d'identification, dont un seul reste "identique" (comme les empreinte digital) :
- L'adresse IP.
- L'adresse MAC (qui s'apparente à un numéro de série).

# 2.1 Les adresses IP
En résumé, une adresse IP (Internet Protocol) peut être utilisée pour identifier un hôte sur un réseau pendant une certaine période, après quoi cette adresse IP peut être attribuée à un autre appareil. 

Premièrement, nous allons décomposé précisement ce dont une adresse IP est constitué :
======================================
[==== Voir Image "IP-Adress.png" ====]
======================================
Une adresse IP est une suite de nombre divisé en 4 octets.
Ce nombre est calculé grâce à l'adressage IP et sous-réseaux (subnetting).
Les adresses IP peuvent changer d'un appareil à l'autre et ne peuvent pas existais deux fois en même temps sur le même réseaux. 

Les adresses IP suivent un ensemble de règles appelées protocoles. Ces protocoles sont la colonne vertébrale du réseau et obligent les appareils à communiquer dans un même langage.
Un appareil peut être sur un réseau privé ou public, et selon le cas il aura une adresse IP publique ou privée.

Une adresse publique sert à identifier l’appareil sur Internet.

Une adresse privée sert à identifier un appareil parmi d’autres sur un réseau local.

Exemple (tableau) :

Nom de l’appareil :   	Adresse IP :	      Type d’adresse :
DESKTOP-KJE57FD	        192.168.1.77	        Privée
DESKTOP-KJE57FD	        86.157.52.21	        Publique
CMNatic-PC	            192.168.1.74	        Privée
CMNatic-PC	            86.157.52.21	        Publique

======================================
[==== Voir Image "IP-privee.png" ====]
======================================

Ces deux appareils ci dessus pourront utiliser leurs adresses IP privées pour communiquer entre eux. Cependant, toutes les données envoyées vers Internet par l’un ou l’autre de ces appareils seront identifiées par la même adresse IP publique (86.157.52.21). Les adresses IP publiques sont fournies par votre fournisseur d’accès à Internet (ou FAI ou ISP en anglais) moyennant un abonnement mensuel (vot).

======================================
[==== Voir Image "FAI/ISP.png" ====]
======================================

À mesure que de plus en plus d’appareils se connectent, il devient de plus en plus difficile d’obtenir une adresse publique qui ne soit pas déjà utilisée. Par exemple, Cisco, un géant de l’industrie du réseau, estimait qu’il y aurait environ 50 milliards d’appareils connectés à Internet d’ici la fin de 2021.

C’est là qu’entrent en jeu les versions d’adresses IP. Jusqu’à présent, nous n’avons parlé que d’une seule version du protocole Internet, appelée IPv4, qui utilise un système de numérotation de 2^32 adresses IP (soit 4,29 milliards) — vous comprenez donc pourquoi il y a une telle pénurie !

IPv6 est une nouvelle version du protocole d’adressage Internet, créée pour résoudre ce problème. Même si elle peut sembler plus complexe, elle offre plusieurs avantages :

Elle prend en charge jusqu’à 2^128 adresses IP (plus de 340 trillions), ce qui règle les problèmes rencontrés avec IPv4.

Elle est plus efficace grâce à de nouvelles méthodes.

La capture d’écran ci-dessous compare une adresse IPv6 et une adresse IPv4.

======================================
[==== Voir Image "IPv6.png" ====]
======================================

Adresses MAC

Les appareils d’un réseau possèdent tous une interface réseau physique, qui est une puce électronique intégrée à la carte mère de l’appareil.
Cette interface réseau reçoit, dès l’usine où elle a été fabriquée, une adresse unique appelée adresse MAC (Media Access Control).

L’adresse MAC est un nombre hexadécimal à douze caractères (un système de numérotation en base 16 utilisé en informatique pour représenter des nombres), regroupé par deux caractères et séparés par des deux-points. Ces deux-points servent simplement de séparateurs. Par exemple : a4:c3:f0:85:ac:2d.

- Les six premiers caractères identifient l’entreprise qui a fabriqué l’interface réseau.

- Les six derniers caractères correspondent à un numéro unique propre à cette interface.

======================================
[==== Voir Image "MAC-Adress.png" ====]
======================================

Détournement d’adresses MAC (MAC spoofing)

Cependant, une chose intéressante à propos des adresses MAC est qu’elles peuvent être falsifiées ou « spoofées » dans un processus appelé spoofing.

Ce spoofing se produit lorsqu’un appareil connecté au réseau se fait passer pour un autre en utilisant son adresse MAC. Quand cela arrive, ça peut casser des dispositifs de sécurité mal conçus qui partent du principe que les appareils présents sur le réseau sont dignes de confiance.

Prends l’exemple suivant : un pare-feu est configuré pour autoriser toute communication vers et depuis l’adresse MAC de l’administrateur. Si un appareil se met à imiter ou « spoof » cette adresse MAC, le pare-feu croira recevoir des communications de l’administrateur alors que ce n’est pas le cas.

Des lieux comme les cafés, les coffee-shops ou les hôtels utilisent souvent le contrôle par adresse MAC pour leurs réseaux Wi-Fi « invité » ou « public ».

Cette configuration peut permettre d’offrir des services différenciés, par exemple une connexion plus rapide moyennant un paiement si tu acceptes de payer par appareil.

Pratique :
THM nous propose un lab qui nous mets en situations justement un wifi qui est controle par adresse MAC (type Hotel) où il faut payer pour le service.

Mise en situation :  Tu remarqueras que le routeur n’autorise pas les paquets de Bob (en bleu) vers le site TryHackMe et les met à la poubelle, tandis que les paquets d’Alice (en vert) passent bien parce qu’elle a payé pour le Wi-Fi. Essaie de changer l’adresse MAC de Bob pour qu’elle soit la même que celle d’Alice et vois ce qui se passe.

Après avoir copié l'adresse MAC, nous avons bien un accès "payant" et ceci s'affiche : 

THM{YOU_GOT_ON_TRYHACKME}