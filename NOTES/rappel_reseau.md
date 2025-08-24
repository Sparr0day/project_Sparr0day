# 🌐 Notes Réseau

## 1. Introduction
- Définition du réseau
- Types de réseaux : LAN, WAN, MAN
- Modèles de référence : OSI vs TCP/IP

---

## 2. Modèle OSI
| Couche | Nom | Rôle principal | Exemple |
|--------|-----|----------------|---------|
| 7 | Application | Interfaces utilisateurs/applications | HTTP, FTP, DNS |
| 6 | Présentation | Format des données, chiffrement | SSL/TLS, JPEG |
| 5 | Session | Gestion des sessions | RPC, NetBIOS |
| 4 | Transport | Fiabilité, segmentation | TCP, UDP |
| 3 | Réseau | Routage, adressage | IP, ICMP |
| 2 | Liaison | Transmission locale, détection erreurs | Ethernet, PPP |
| 1 | Physique | Transmission binaire brute | Câbles, signaux |

---

## 3. Modèle TCP/IP
- Couches :
  - Application (HTTP, FTP, SMTP, DNS…)
  - Transport (TCP, UDP)
  - Internet (IP, ICMP, ARP)
  - Accès réseau (Ethernet, Wi-Fi)

### Comparaison OSI vs TCP/IP
- OSI : modèle théorique (7 couches)
- TCP/IP : modèle pratique (4 couches)

---

## 4. Protocoles Importants

### 4.1 TCP
- Fiable, orienté connexion
- Mécanismes : 3-way handshake, ACK, retransmission
- Utilisation : HTTP, FTP, SMTP

### 4.2 UDP
- Non fiable, sans connexion
- Faible overhead
- Utilisation : DNS, VoIP, streaming

### 4.3 IP
- Adressage (IPv4, IPv6)
- Routage
- Pas de garantie de livraison

---

## 5. Adressage IP
- IPv4 : 32 bits, classes A/B/C
- IPv6 : 128 bits
- Masque de sous-réseau
- CIDR (ex. 192.168.1.0/24)

### Outils
- `ping`
- `traceroute`
- `ipconfig` / `ifconfig`

---

## 6. Routage
- Routage statique vs dynamique
- Protocoles : RIP, OSPF, BGP

---

## 7. Sécurité réseau
- Firewall
- NAT
- VPN
- IDS/IPS

---

## 8. Commandes utiles
```bash
ping google.com
traceroute 8.8.8.8
netstat -tulpn
tcpdump -i eth0
