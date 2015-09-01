<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Rappels sur TCP/IP](#rappels-sur-tcpip)
	- [Réseau local](#rseau-local)
	- [Réseau Internet](#rseau-internet)
	- [Commutation de paquets](#commutation-de-paquets)
- [Modèle OSI](#modle-osi)
	- [Modèle OSI de l'ISO](#modle-osi-de-liso)
		- [Les méthodes d'accès :](#les-mthodes-daccs-)
		- [Les modes de diffusion :](#les-modes-de-diffusion-)
		- [Les modes de diffusion sur un réseau local](#les-modes-de-diffusion-sur-un-rseau-local)
		- [La couche réseau](#la-couche-rseau)
		- [La boucle locale](#la-boucle-locale)
		- [Architecture opérateur](#architecture-oprateur)
		- [La couche transport](#la-couche-transport)
		- [La couche application](#la-couche-application)
	- [Le mécanisme d'encapsulation](#le-mcanisme-dencapsulation)
	- [Encapsulation](#encapsulation)
- [Modèle TCP/IP](#modle-tcpip)
	- [Comparaison entre OSI et TCP/IP](#comparaison-entre-osi-et-tcpip)
- [TCP/IP](#tcpip)
	- [Les réseaux locaux](#les-rseaux-locaux)
		- [Communication sur les réseaux locaux](#communication-sur-les-rseaux-locaux)
		- [Trame Ethernet](#trame-ethernet)
		- [Topologie des réseaux](#topologie-des-rseaux)
		- [De Ethernet à IP](#de-ethernet-ip)
		- [MAC vs IP](#mac-vs-ip)
		- [Qu'est-ce qu'une adresse IPv4 ?](#quest-ce-quune-adresse-ipv4-)
		- [Adresses remarquables](#adresses-remarquables)
		- [ARP](#arp)
<!-- /TOC -->

# Rappels sur TCP/IP

## Réseau local

Adresses MAC (couche 2)

Communications en broadcast :

- Une machine émet le paquet sur le réseau
- L'adresse du destinataire est dans le paquet
- Toutes les machines du réseau reçoivent le paquet
- Seule la machine destinatrice traite le paquet

## Réseau Internet

Lorsque l'on sort du réseau local, on communique grâce aux couples IP et TCP/UDP

Communication point-à-point :

- Communication entre 2 machines
- Cette communication doit passer entre les machines intermédiaires

## Commutation de paquets

Découper les données en petite taille pour réduire dans le but de faciliter les échanges en milieu hétérogènes

- chaque bloc contient l'adresse du destinataire
- les blocs sont réassemblés par le destinataire

# Modèle OSI

## Modèle OSI de l'ISO

Modèle de référence composé de 7 couches.

A chaque couche correspond une fonction précise, ne définit par un protocole mais un service.

![OSI](http://reussirsonccna.fr/wp-content/uploads/2012/02/7couches_archi11.png)

[modèle OSI](http://reussirsonccna.fr/modele-osi/)

### Les méthodes d'accès :

Simplex (unidirectionnelle)

Duplex (bidirectionnelle asychrone)

Full Duplex (bidirectionnelle simultanée)

### Les modes de diffusion :

Unicast : A -> B

Broadcast : A => All

Multicast : A => Ensemble de destinataires

La couche de liaison de données

- Règle les conflits d'accès du canal de transmission
- Ethernet
- 802.2 CSMA/CD

### Les modes de diffusion sur un réseau local

Unicast : Communication directe vers une seule machine, Adresse MAC paire

Broadcast : Communication avec toutes les stations : FF-FF-FF-FF-FF-FF

Multicast : Communication vers un groupe de machines, le 1er est impair

### La couche réseau

Résout les problèmes de routage

Assure le traitement entre les couches basses et hautes

IP

ICMP

ARP

### La boucle locale

Représente ce qui relie l'utilisateur à l'équipement du réseau de son FAI

Filaire : xDSL

Fibre : FTTx

Electromagnétique : WIMAX et GSM

### Architecture opérateur

BOX

DSLAM

BAS

RBCI

FAI


### La couche transport

Communication de bout en bout grâce à cette couche

Assurer une certaine qualité de transmission

- contrôle de flux
- sequencement
- acquittemenet des messages
- multiplexage d'applications

TCP

- protocole avec connexion
- "On est sûr que l'info arrive à son destinataire"

UDP

### La couche application

Constituée des programmes/services

Messagerie, transfert de fichier, navigateur web ...

## Le mécanisme d'encapsulation

- Chaque couche du modèle OSI ajoute des informations au message à destination de la même couche mais chez le récepteur
- Ces informations ne concernent que la couche du récepteur, en aucun cas les couches du dessus ou du dessous ne sont concernées


![encapsulation OSI](https://user.oc-static.com/files/284001_285000/284769.png)


## Encapsulation

Emetteur :

- une couche ne communique qu'avec la couche qui la précède et qui la suit
- Lors de l'émission d'un message depuis la couche 7, chaque couche ajoute son "élément" propre
- Cet élément sera "lu" par la couche correspondante du destinataire
- => Encapsulation

Destinataire :

- Le message arrive par la couche 1 pour aller à la couche 7
- Chaque couche que le message traverse "récupère" l'information qui lui est proche
- => Désencapsulation

# Modèle TCP/IP

Modèle DOD

4 couches :

- Couche application
- Couche transport
- Couche internet
- Couche accès réseau

## Comparaison entre OSI et TCP/IP

![comparaison](http://cisco.goffinet.org/s1/OSIdetailledNewPage1.png)

# TCP/IP

## Les réseaux locaux

trame éthernet

les trames sont émisent en broadcast

Chaque trame est reçue par l'ensemble des équipement situées sur le même lien

Ces trames ont une taille MTU

Les équipements réseau sont identifiés par leur interface

Chaque interface du réseau possède une adresse MAC presque unique de 6 octets, les 3 premiers identifient le contructeur de la carte

### Communication sur les réseaux locaux

On utilise les adresses MAC pour communiquer sur les réseaux locaux

Principe de communication :

- Broadcast de la trame avec l'adresse MAC de la machine cible
- Tous les équipements recoivent cette trame
- Seule la machine cible traite l'information

### Trame Ethernet

![trame](http://igm.univ-mlv.fr/~dr/XPOSE2007/vlanparlegrandquinapascomprislesconsignes/trame8021Q.jpg)

### Topologie des réseaux

![reseau](http://www.ybet.be/hardware2_ch3/hard2ch3_2.gif)

### De Ethernet à IP

Problèmes à résoudre :

- Communiquer avec tout le monde, n'importe où, n'importe comment
- Accessible par tout le monde
- Une machine doit pouvoir être identifiée par : un nom, une adresse unique, une route pour y accéder
- Problématique des noms est résolu grâce au DNS

### MAC vs IP

Une adresse MAC identifie une interface sur un réseau local :

- plus ou moins unique
- c'est une adresse physique

Une adresse IP identifie une machine sur un réseau :

- aucune dépendance vis-à-vis du matériel
- C'est une adresse logiqe

On n'agit pas sur les mêmes couches des modèles OSI / TCP/IP


### Qu'est-ce qu'une adresse IPv4 ?

Une suite de 4 "mots" écrits en décimal

Une adresse : 32 bits : 4 octets

Une adresse : 4 octets entre 0 et 255

Une paire (netid, hostid)

netid identifie le réseau

hostid identifie la machine sur le réseau

### Adresses remarquables

127.X.X.X (127.0.0.1) localhost

Privé 10.0.0.0/8 192.168.0.0/16 non routés

Adresse de broadcast : dernière adresse du réseau

Le besoin :

- la communication entre machines ne peut s'effectuer qu'à travers l'interface physique
- Les applicatifs ne connaissant que des adresses IP, comment établir le lien adresse IP/ adresse physique
- Les machines sur un réseau local ne communiquent que par Ethernet

La solution : ARP

Mise en place dans TCP/IP d'un protocole de bas niveau appelé ARP

Rôle fournir à une machine donnée l'adresse physique d'une autre machine située sur le même réseau à partir de l'adresse IPv4 de la machine destinatrice

La technique :

- Diffusion d'adresse sur le réseau physique
- La machine d'adresse IPv4 émet un message contenant son adresse physique
- Les machines non concernées ne répondent pas
- Gestion cache pour ne pas effectuer de requête ARP à chaque émission

### ARP

Naivement pour chaque paquet IPv4 on ferait un échange ARP

Problème : traffic énorme

Solution : chaque machine conserve les dernières transactions dans un cache (table ARP)
