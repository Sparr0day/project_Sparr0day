## 1 Introduction aux topologies LAN
Au fil des années, différentes conceptions de réseaux ont été expérimentées et mises en œuvre. En réseautique, lorsque l’on parle de “topologie”, on fait référence à la conception ou à l’agencement physique/logique du réseau. Voyons ci-dessous les avantages et inconvénients de certaines topologies courantes.

# 1.1 Topologie en étoile (Star Topology)
======================================
[==== Voir Image "IP-Adress.png" ====]
======================================

Le principe principal de la topologie en étoile est que chaque appareil est connecté individuellement via un dispositif central comme un switch ou un hub. 
C’est la topologie la plus répandue aujourd’hui grâce à sa fiabilité et sa scalabilité, malgré son coût plus élevé.

Toute information envoyée à un appareil dans cette topologie transite par le dispositif central auquel il est connecté.

Avantages :

- Très scalable : il est facile d’ajouter de nouveaux appareils à mesure que le réseau grandit.
- Plus fiable qu’une topologie plus simple, car les défaillances locales n’affectent pas l’ensemble du réseau.

Inconvénients :

- Plus coûteuse en câbles et matériel réseau dédié.
- Maintenance plus complexe à mesure que le réseau s’agrandit, ce qui peut compliquer le dépannage.
- Point central unique : si le dispositif central tombe en panne, les appareils connectés ne peuvent plus envoyer ni recevoir de données. Heureusement, ces équipements centraux sont souvent robustes.