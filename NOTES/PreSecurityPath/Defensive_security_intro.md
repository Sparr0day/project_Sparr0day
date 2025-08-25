## Introduction
La sécurité défensive, connu sous le nom de Blue team, est chargé de préparé et proteger pro activement les infrastructures informatiques d'une entreprises.
Elle est concerné par deux principales tâches : 
- Prévenir la survenue d’intrusions.
- Détecter les intrusions lorsqu’elles se produisent et y répondre de manière appropriée.

Les tâches liées à la sécurité defensive peuvent aussi être : 
- Sensibilisation à la cybersécurité
    Former les utilisateurs aux attaques informatiques, telles que le phishing et l’ingénierie sociale.
- Documentation et gestion des systèmes
    Il est essentiel de connaître les systèmes de l’organisation afin de pouvoir les protéger efficacement.
- Sécurité préventive
    Les pare-feu et les systèmes de prévention des intrusions constituent la première ligne de défense. Ces dispositifs contrôlent le trafic entrant et sortant du réseau et empêchent le trafic malveillant d’y pénétrer.
- Journalisation et surveillance
    La journalisation complète (logs) des activités du réseau et des systèmes est essentielle pour détecter une menace ou une activité non autorisée.
- Cadres, politiques et procédures
    L’élaboration de politiques de sécurité solides permet de garantir que les équipements de l’organisation sont utilisés de manière appropriée.

## 1.Exploring the SOC
Dans la Blue team, il existe différents éléments qui permettent d'assuré la sécurité défensive dont : le SOC

- Qu'est-ce qu'un SOC (Security Operations Centre ou Centre des Opérations de Sécurité en français) ?

Le SOC est une équipe qui surveille le réseau et tout les systèmes afin de détecter des anomalies ou événement louches qui pourraient être malveillants.
Voici quelques-unes des principales missions d’un SOC :

- Tendances & veille sur les vulnérabilités
    Se tenir informé des dernières tendances et vulnérabilités dans le domaine est une compétence essentielle pour comprendre les risques auxquels une organisation est exposée.

- Violations de politiques
    Une politique de sécurité est un ensemble de règles définissant la manière dont les actifs (systèmes) d’une organisation doivent être utilisés et protégés. L’équipe SOC surveille le respect de ces règles.

- Activités non autorisées & illégales
    L’équipe SOC établit une base de référence du comportement et des activités acceptables. Toute déviation par rapport à cette référence fait l’objet d’une enquête. Les activités illégales  exposent l’organisation à un risque accru.

- Détection d’intrusions & de violations
    Peu importe le niveau de protection d’une organisation, le risque de violation demeure. L’équipe SOC est responsable de détecter et de répondre à ces incidents.

## 2.Digital Forensics
Le forensics c'est quand on utilise des technique de "criminalistique" sur des appareils (téléphone/ordinateur) genre on enquête pour trouver des preuves etc dans le monde numérique.
Ca permets de comprendre ce qui s'est passé lors d'un piratage ou lors d'une attaque.

Cela peut impliquer l'examen d'informations provenant de :

- Le disque dur (File System)
On regarde les programmes installés, les fichiers créés, effacés ou même partiellement écrasés.


- La Mémoire système
Si un attaquant a infecté la machine avec un programme malveillant sans l'enregistrer sur le disque, la mémoire peut être analysé pour découvrir des détails sur comment le programme fonctionne.


- Les journaux du systeme (System Logs)
Les fichiers de logs notent  plein d'information sur ce qu'il se passe sur un système. Même si l'attaquant essait d'effacer toutes traces, certaines traces peuvent restées.


- Les journaux réseau (Network Logs)
Les logs du traffic réseaux peuvent aider a répondres si une attaque a eu lieu et savoir comment ca s'est déroulé.

## 3.Incident Response
La réponse aux incident est comment les organisations organise et gère les évenement lié a la sécurité comme les failles, les leaks ou directement les attaques. 
Le processus d'une réponse d'incident est une suite défini d'étapes a suivre pour minimiser les dégats, contenir la menace et rétablir les service rapidement.

Un processus se fait en plusieurs étapes : 

- Preparation
Mettre en place les ressources pour gerer un incident. Cela inclus la création d'une équipe spéciale pour gérer les incidents, une infrastructure et des outils pour réagir ainsi que des sensibilisations des employés au phishing par exemple ou aux différentes attaques.

 
- Detection et Analyse
Utiliser des outils et processus pour detecter les incidents et voir jusqu'où ils s'étendent (leurs scopes) et leur criticité. Les logs peuvent être analysé pour les évenement suspicieux.

 
- Confinement, Éradication et Récupération
Limité l'impacte de l'incident, faire en sorte d'empecher la diffusion du virus et éliminé la cause et donc restauré les systèmes affecté.
Confinement : limiter les dégâts (par ex. isoler un ordinateur infecté pour que le virus ne se propage pas).
Éradication : supprimer la cause (le virus, le malware, la faille…).
Récupération : remettre les systèmes affectés en état et s’assurer qu’ils fonctionnent normalement.
 
- Activité Post-Incident
Une fois tout réglé, on fait un retour d’expérience :
Qu’est-ce qui a bien/mal été fait ?
Comment éviter que ça recommence ?
Faut-il améliorer la formation ou les outils ?

## 4.Practical Example of Defensive Security
THM nous balance un cas pratique !
THM nous mets dans la peau d'un anayste SOC pour une entreprise. 
On a l'accès à l'outil SIEM (Security Information and Event Management) interne de l'entreprise qui récolte les informations et évenement lié à la sécurité de plusieurs sources et les présentes sous un dashboard.
Si le SIEM trouve quelque chose de suspicieux, une alerte est généré.

THM nous mets donc à disposition ce SIEM pour qu'on puisse mettre la main à la pâte et avoir une expérience similaire à ce qu'un analyste en cyber sécurité pourrait rencontré.

Nous nous retrouvons face à 3 onglets : 

- SIEM Dashboard
=> Nous avons l'alerte d'une tentation de connexion non autorisé via une adresse IP
- IP Scanner
=> Grâce au scanner nous pouvons identifier sa localisation, ici ça viens de chine et le nom de domaine est : chinamobileltd.thm
=> Nous remonter l'information au Leader analyst SOC
- Firewall
=> Nous pouvons bloquer cette adresse IP grâce à une règle du Firewall.

Nous avons réussi la tâche ! :D


Bonus : 
Il existe plein de bases de données gratuites et ouvertes (open-source) comme AbuseIPDB ou Cisco Talos Intelligence.
Avec elles, tu peux :
vérifier la réputation d’une adresse IP (si elle est connue comme malveillante),
vérifier sa localisation.
🔎 Les analystes en cybersécurité utilisent souvent ces outils pour enquêter quand ils reçoivent une alerte.
💡 Et toi aussi tu peux aider à rendre Internet plus sûr : si tu découvres une IP malveillante, tu peux la signaler (par exemple sur AbuseIPDB).
