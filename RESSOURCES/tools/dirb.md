DIRB est un outil en ligne de commande utilisé en cybersécurité pour le brute-forcing de répertoires et fichiers web. Il envoie des requêtes HTTP basées sur des dictionnaires afin de découvrir des ressources cachées ou non répertoriées (par exemple : /admin, /login, /backup.zip).
Il est souvent employé lors de tests d’intrusion pour cartographier la surface d’attaque d’un site web.

# Exemple pratique :
Un pentester scanne http://example.com/ et découvre :

/backup/ contenant un fichier db_backup.sql

/test/ avec un script non protégé test_login.php

Ces découvertes peuvent révéler des failles critiques si elles sont accessibles publiquement

# Quelques exemples d'utilisations : 

- Scan basique d’un site :
$ dirb http://example.com/
Lance un scan par défaut du site example.com en utilisant le dictionnaire intégré de DIRB.

- Scan avec un dictionnaire personnalisé :
$ dirb http://example.com/ /usr/share/wordlists/common.txt
Utilise le fichier common.txt comme liste de mots pour rechercher des répertoires et fichiers.

- Scan avec extension de fichier :
$ dirb http://example.com/ -X .php,.bak,.txt
Cherche uniquement les fichiers avec les extensions .php, .bak et .txt

- Scan d’un sous-répertoire précis :
$ dirb http://example.com/admin/
Cible uniquement le répertoire /admin/ du site.

- Scan en utilisant un proxy (ex. Burp Suite) :
$ dirb http://example.com/ -p http://127.0.0.1:8080
Permet de passer par un proxy, pratique pour intercepter et analyser les requêtes.

- Exclusion de codes HTTP :
$ dirb http://example.com/ -N 404
Ignore les réponses 404 Not Found pour réduire le bruit.