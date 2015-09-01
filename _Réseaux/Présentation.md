<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Rappels sur TCP/IP](#rappels-sur-tcpip)
	- [Réseau local](#rseau-local)
	- [Réseau Internet](#rseau-internet)
	- [Commutation de paquets](#commutation-de-paquets)
- [Modèle OSI](#modle-osi)
	- [Modèle OSI de l'ISO](#modle-osi-de-liso)
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

![OSI](/images/2015/09/7couches_archi11.png)

[modèle OSI](http://reussirsonccna.fr/modele-osi/)

Les méthodes d'accès :

Simplex (unidirectionnelle)

Duplex (bidirectionnelle asychrone)

Full Duplex (bidirectionnelle simultanée)

Les modes de diffusion :

Unicast : A -> B

Broadcast : A => All

Multicast : A => Ensemble de destinataires

La couche de liaison de données

- Règle les conflits d'accès du canal de transmission
- Ethernet
- 802.2 CSMA/CD
