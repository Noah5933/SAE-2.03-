# **Rapport SAÉ 2.03**
---

## ++Sommaire++

1. [Préparation de la machine virtuelle](#préparation-de-la-machine-virtuelle)
2. [Installation de l’OS](#installation-de-los)
3. [Préparation du système](#préparation-du-système)
4. [À propos de la distribution Debian](#à-propos-de-la-distribution-debian)
5. [Installation préconfigurée](#installation-préconfigurée)

# ++Préparation de la machine virtuelle++

## Étape 1 : Installer Oracle VirtualBox  

Si ce n’est pas déjà fait, veuillez télécharger le logiciel Oracle VirtualBox à l’adresse suivante : https://www.virtualbox.org/wiki/Downloads . 

Installez-le et lancez le logiciel. 

Après quelque seconde ou minute, vous devriez avoir un menu semblable à celui-ci :  

![](https://projetcartylion.fr/wp-content/uploads/2020/08/Placeholder-300x300.png)

Félicitation ! Vous avez installé Oracle VirtualBox avec succès et pouvez désormais passer à l’étape suivante de ce guide d’installation !  

## Étape 2 : Création une nouvelle machine virtuelle :  

Dans cette étape, vous allez apprendre à configurer votre 1ere machine virtuelle, pour ce faire commencer par cliquer sur le bouton « Nouvelle » situé en haut au milieu. 

Une nouvelle fenêtre s’ouvre à vous et devrait ressembler à ça :  

 ![](https://projetcartylion.fr/wp-content/uploads/2020/08/Placeholder-300x300.png)

Ajoutez-lui ensuite un nom, faites attention à bien lui donner un nom distinctif, ici on a donc mis **sae203**. 

Par défaut, le logiciel utilise un chemin prédéfini pour installer la machine virtuelle, ce chemin est : C:\Users\*nom_utilisateur*\VirtualBox VMs 

Il faut le changer en C:\Users\*nom_utilisateur*\VirtualBox, pour l'auto-installation future.

Ce chemin est sélectionné par défaut mais peut être changé à votre guise. 

Dans la sous étape, nous allons nous baser sur la distribution Debian de Linux et nous avons pris Debian 64-bit de nom de code "bookworm".

Ensuite cliquez sur « Type » et sélectionner « linux » puis cliquez sur « subtype » et sélectionné « Debian (64-bit)». Ceci fait, le logiciel sélectionnera une version de base en 64bit. 

Appuyez désormais sur « finish ». 

## Étape 3 : Configuration de la machine virtuelle :  

Maintenant que votre machine virtuelle est créée, vous devez la paramétrer. 

Pour ce faire, cliquez sur votre machine virtuelle fraichement créer et sélectionner « Configuration » 

Une nouvelle fenêtre devrait s’ouvrir et ressembler à ça :  

![](https://projetcartylion.fr/wp-content/uploads/2020/08/Placeholder-300x300.png)

Par défaut, le logiciel utilise des paramètres demandant peu de ressources pour fonctionner sur le PC les moins performant, si votre PC est puissant alors je vous conseille de modifier ces paramètres : Descendez dans « system » et augmentez la mémoire jusque 2048 Mo et 20 Go de stockage.

Ensuite, vous aller installer le système d’exploitation que vous souhaitez, pour ce faire cliquez sur l’onglet « Stockage » et sélectionné le petit disque bleu en dessous de « contrôleur IDE » et sélectionné une nouvelle fois le disque bleu, puis appuyez sur l’option « Choose a disk file » comme dans l’image indiqué ci-contre :  

![](https://projetcartylion.fr/wp-content/uploads/2020/08/Placeholder-300x300.png)

Ensuite sélectionné l’image disque contenant votre système d’exploitation et appuyez sur « OK », dans notre cas ça sera l'ISO disponible sur le site officiel de Debian (donc Debian 12). 

* Que signifie “64-bit” dans “Debian 64-bit” ?

> 64 bits signifie que c’est un logiciel fait pour un [processeur de type *64 bits*](https://fr.wikipedia.org/wiki/Processeur_64_bits), un processeur plus
puissant qu’un *32 bits*, fait pour avoir un plus __grand nombre de calculs par seconde__. \
Cela peut signifier que la version Debian 32-bit n’est pas exécutable par un ordinateur 64-bit, ils ont donc
besoin d’une version spécifique pour le 64-bit.

* Quelle est la configuration réseau utilisée par défaut ?

> La configuration réseau par défaut est le **NAT**, un réseau où la machine virtuelle a accès à Internet
et a donc sa propre adresse IP par le DHCP VirtualBox *et non par notre réseau local*, ainsi les
machines physiques de notre réseau n’ont pas accès à la machine virtuelle car elle n’a pas **d’IP par
le DHCP local**.

* Quel est le nom du fichier XML contenant la configuration de votre machine ?

> Il s’appelle tout simplement **sae203.vbox**, à ouvrir avec un éditeur de texte *(l’exécuter lancera la VM)*, on y retrouve tous les paramètres comme :
>1. Le nombre de processeurs, 
>2. La mémoire allouée,
>3. L’UUID du hard disk, de l’image 
>4. Leur emplacement sur la machine locale...\
>
>C’est bien un fichier xml car la 1ere ligne est : **\<?xml version="1.0"?>.** \
L’emplacement du fichier est relatif à chaque machine, dans mon cas : \
*C:\Users\Toyger\VirtualBoxVMs\sae203\.*

*  Sauriez-vous le modifier directement ce fichier de configuration pour mettre 2 processeurs à votre
machine ?

> Dans le fichier, on le retrouve dans la balise **Hardware** puis la balise **CPU count** = 2, dans notre cas,
CPU count = 1, car nous n’avons assigné qu’un **seul processeur à la VM**.

---

## ++Installation de l'OS++

Lancez votre machine virtuelle, vous allez pouvoir lancer l'installation de votre système d'exploitation.
Pour celà, au fur et à mesure vous allez devoir insérer les informations qui suivent :

* Le nom de la machine sera "serveur"
* Pas de domaine à mettre
* Le pays et la langue sera France/Français
* Avec le miroir de Polytech http://debian.polytech-lille.fr sans proxy
* Création des utilisateurs User avec login user et mot de passe user, et du root avec mot de passe root
* Sélections des logiciels de démarrage :
    - [x] Environnement de bureau Debian
    - [ ] GNOME
    - [ ] Xfce
    - [ ] bureau GNOME Flashback
    - [ ] KDE Plasma
    - [ ] Cinnamon
    - [x] MATE
    - [ ] LXDE
    - [ ] LXQt
    - [x] serveur web
    - [x] serveur SSH
    - [x] utilitaires usuels du système

*  Qu’est-ce qu’un fichier iso bootable ?
> Un fichier ISO est un fichier **qui remplace un CD/DVD**. Il permet l’exécution de programme
comme un système d’exploitation sur une clé USB ( winzip; pc mag).

*  Qu’est-ce que MATE ? GNOME ?
> **MATE est un environnement de bureau**. MATE est basé sur GNOME. Il a été créer suite a
GNOME 3 jugé insatisfaisant par la communauté. **GNOME est l’environnement de bureau par
défaut sur de nombreuse distribution Linux** (Wikipédia, Mate-desktop.org, wiki.debian.org).

* Qu’est-ce qu’un serveur web ?
> Un serveur web est un serveur qui **fournit les fichiers nécessaires à l’affichage d’une page web a
l’utilisateur**. Il peut aussi stocker des données. (solarwinds, le mag it).

* Qu’est-ce qu’un serveur ssh ?
> Un serveur SSH est un serveur utilisant le protocole SSH. **Le protocole SSH permet de donner
l’accès à distance à un autre ordinateur**. Toute les commande effectue depuis le terminal hôte seront
exécuté sur le terminal cible. (le mag it, zah.uni-heidelbzeg.de).

* Qu’est-ce qu’un serveur mandataire ?
> Un serveur mandataire est un serveur entre un serveur et un ordinateur. **Il permet la connexion en y
ajoutant une couche de sécurité supplémentaire** (it-connect, support-apple, cyber-management-school.com ).

---

## ++Préparation du système++
* Comment peux-ton savoir à quels groupes appartient l’utilisateur user ?
> Effectuer la commande suivante dans un terminal Linux : **groups user**, qui donne tous les groupes
auxquels appartient user : 

`user, cdrom, floppy, sudo, audio, dip, video, users, netdev, lpadmin, scanner`
> On retrouve bien le groupe sudo après y avoir ajouté user.
---

## ++À propos de la distribution Debian++

* Quel est la version du noyau Linux utilisé par votre VM ? N’oubliez pas, comme pour toutes les
questions, de justifier votre réponse.

> En effectuant la commande : cat /etc/os-release, on obtient :
```
PRETTY NAME= «Debian GNU/Linux 12 (bookworm) »
NAME = « Debian GNU/Linux »
VERSION_ID = « 12 »
...(D’autres informations sont affichées).
```
> On retrouve bien notre distribution (Debian GNU/Linux) qui serait à la version 12 (VERSION_ID).

* À quoi servent les suppléments invités ? Donner 2 principales raisons de les installer.

> Les suppléments invités sont des **pilotes adaptés aux systèmes invités** (Windows, GNU/Linux ...)
qui servent à **relier facilement une machine hôte et une machine virtuelle (invitée) installée dessus**.
Installer ces suppléments permet de **partager entre les deux machines le presse papier ou encore les
dossiers**. La gestion de la souris est aussi plus dynamique lorsqu’elle se déplace entre le système
hôte et le système invité.

* À quoi sert la commande mount (dans notre cas de figure et dans le cas général) ?
> Cette commande permet de **monter des systèmes de fichiers dans le répertoire d'un système de
fichiers déjà existant**. Elle peut être utilisée pour que des périphériques de stockage (disque dur, clé
USB, CD/DVD ...) soient **accessibles à l’utilisateur et à l’ensemble du système**.

---
## ++Installation préconfigurée++

* Qu’est-ce que le Projet Debian ? D’où vient le nom Debian ?
> Le projet Debian est un **groupe mondial de volontaires** qui s'efforcent de produire un **système d'exploitation qui soit composé exclusivement de logiciels libres**. Le principal produit de ce projet est la distribution Debian GNU/Linux, qui inclut le noyau Linux ainsi que des milliers d'applications préempaquetées, **d’après le site officiel**.

> Le nom Debian provient d’une **concaténation** entre les parties des prénoms du créateur et sa petite amie de l’époque (**==Ian== Murdock et ==Deb==ra Lynn → Deb Ian)**.

* Il existe 3 durées de prise en charge (support) de ces versions : la durée minimale, la durée en
support long terme (LTS) et la durée en support long terme étendue (ELTS). Quelle sont les durées
de ces prises en charge ?
> La durée minimale est de **3 ans**, la plupart des anciennes versions ont été supporté à ce minimum (Debian 2.2, 3.1, 4.0).
> La durée support long terme est de **5 ans**.
> La durée support long terme étendue est de **10 ans** (5 ans offert par LTS Project et 5 supplémentaires

* Pendant combien de temps les mises à jour de sécurité seront-elles fournies ?
> Les mises à jour de sécurité sont prises en charge pendant **3 ans**, car en avoir plusieurs en même temps est très difficile.

*  Combien de version au minimum sont activement maintenues par Debian ? Donnez leur nom
générique (= les types de distribution).
> Il y a au **minimum 3 versions qui sont activement maintenues par Debian** : Stable, testing et unstable. La version Stable est celle qu’on télécharge **par défaut** et celle qui est la plus recommandé pour les utilisateurs peu qualifiés.

* Chaque distribution majeur possède un nom de code différent. Par exemple, la version majeur
actuelle (Debian 12) se nomme bookworm. D’où viennent les noms de code données aux
distributions ?
> Les noms de chaque distribution debian viennent des différents noms des personnages de **Toy Story**. La 1ere version de Debian s’appelait buzz en référence a Buzz l’éclair qui est un personnage phare de l’univers de Toy Story. Ainsi dans l’ordre, nous avons:

| Version Debian | Nom |
---|---|
| 1 | Buzz |
| 2 | Rex |
|3 | Bo 
|4 | Hamm
| 5 | Slink 
| 6 | Potato 
|7 | Woody 
| 8 | Sarge |
| 9 | Etch 
|10| Lenny
|11| Squeeze
|12| Wheezy
|13| Jessie
|14| Stretch
|15| Buster
|16| Bullseye
|17| ==Bookworm==
|18| Trixie
|19| Sid
> **Le fait d’utiliser les noms des personnages de Toy Story viens de Bruce Perens et travaillait à l’époque chez Pixar qui est en charge des films Toy Story**.

*  L’un des atouts de Debian fut le nombre d’architecture (≈ processeurs) officiellement prises en
charge. Combien et lesquelles sont prises en charge par la version Bullseye ?
> Il y a actuellement **9** architectures qui sont officiellement pris en charge par Debian 12 (Bookworm). Ces derniers sont : 
```
    AMD64 & Intel64
    Intel x86-based
    ARM
    ARM avec matériel FPU
    ARM 64 bits
    MIPS 64 bits (petit-boutien)
    MIPS 32 bits (petit-soutien)
    Power Systems
    IBM S/390 64 bits.
```

* Première version avec un nom de code
    *
    *
    *
*  Dernière nom de code attribué
    *
    *
    *

Note de bas de page[^ref]

[^ref]: Description note de bas de page