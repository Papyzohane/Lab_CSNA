# Lab_CSNA
Ce dépôt contient l'ensemble un lab avec l'ensemble des ressources, topologies et configurations nécessaires à la préparation de la certification Stormshield Network Administrator (CSNA). L'objectif est de fournir un environnement de test complet pour maîtriser l'administration des pare-feu SNS (Stormshield Network Security).

🏗️ Architecture du Lab

L'environnement est basé sur une topologie multi-entreprises reliées par un réseau externe (192.36.253.0/24). Chaque site dispose de :

-Firewall SNS : Modèle SN210W (Version logicielle 4.6.11).
-Serveur Debian : Hébergeant les services DNS, WEB, FTP et MAIL.
-Poste Client : Station Windows pour l'administration et les tests de flux.

Plan d'adressage (Exemple Compagnie E / n°5)
-Interface IN : 192.168.5.254/24
-Interface DMZ : 172.16.5.254/24
-Interface OUT : 192.36.253.50/24
-Réseau Interne : 192.168.5.0/24
    
<img width="814" height="610" alt="image" src="https://github.com/user-attachments/assets/c8782f2a-079f-497a-8d51-4456fdee60b3" />
