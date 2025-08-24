## 1. Introduction
La sécurité par l'attaque est le fait de penser comme un hacker. le but est de reperer des failles dans les système/applications et/ou exploités des bugs pour obtenirs un accès non autorisé.

Le but de ce chapitre est de ce mettre dans la peau d'un hacker et d'attquer nos premiers site web d'une manière sure et legal grâce aux labs que propose TryHackMe. 

## 2. Starting the labs
Ici TryHackMe mets à notre disposition une machine virtuelle pour s'entrainer.
Dans cette VM, c'est une fausse application bancaire nommée "FakeBank".
# 2.1 Accèdez à la suite
Pour la première étape : THM nous demande de renseigné le numéro de compte de la fausse application bancaire.

## 3. Your first hack
Nous avons un compte clien standard.
Le but de ce premier exercice est de détourner l'application afin de s'ajouter autant d'argent qu'on veux sur ce compte.

La première choses à faire et l'une des plus simple pour detourner l'accès et pouvoir faire des choses qu'un utilisateur lambda ne pourra pas faire.

Le moyen le simple pour tenter d'hacker une application est de trouver des fonctionnalités caché dans l'app.
Parfois les applications rendent accessible des fonctionnalités sensibles au utilisateur via des URLs "secrètes".
Si nous arrivons a trouver de tel URL, nous pourrons alors faire des choses que les utilisateurs lambda ne sont pas censé pouvoir faire.

Pour trouver ces URLs, nous allons utilisé un outils nommé "dirb". Cet outil utilise une approche brute force. En effet, il prend une liste de potentiel nom de page et les tests une par une pour voir si elles existent sur le site web.
Cet approche fonctionne car les gens utilisents des noms de pages facile a deviner (souvent les mêmes).
# 3.1 Début de l'exercice
Sur la VM proposé par THM, nous lançons un terminal.
Dans ce terminal nous allons utilisé l'outil "dirb" :
$ dirb *url du site* (ici http://fakebank.thm)

dirb lance le process et nous donne plusieurs informations :

- L'url sur laquelle on test
- Le dictionnaires(liste) de mots qu'on utilise pour bruteforce les routes.

dirb process dans le test des différentes routes et nous sorts deux routes accessible : 
http://fakebank.thm/bank-deposit                    
http://fakebank.thm/images

On va donc tester ces routes en commençant par la "/bank-deposit" qui semble plus importantes pour detourner l'accès.

BINGO : 
La route nous emmènent sur une page "STAFF ONLY" qui permet de créditer autant d'argent qu'on veut sur n'importe quel compte.
Ici il nous reste juste a renseigné notre numéro de compte et l'argent que nous voulons créditez dessus.