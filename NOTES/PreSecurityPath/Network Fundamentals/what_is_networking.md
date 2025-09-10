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
[==== Voir Image "IP-Adress.png" ====]

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