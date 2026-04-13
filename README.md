# Lab_CSNA

Ce dépôt contient l'ensemble un lab avec l'ensemble des ressources, topologies et configurations nécessaires à la préparation de la certification Stormshield Network Administrator (CSNA). L'objectif est de fournir un environnement de test complet pour maîtriser l'administration des pare-feu SNS (Stormshield Network Security).

🏗️ Architecture du Lab

<img width="814" height="610" alt="image" src="https://github.com/user-attachments/assets/c8782f2a-079f-497a-8d51-4456fdee60b3" />

L'environnement est basé sur une topologie multi-entreprises reliées par un réseau externe (192.36.253.0/24). Chaque site dispose de :

    Firewall SNS : Modèle SN210W (Version logicielle 4.6.11).

    Serveur Debian : Hébergeant les services DNS, WEB, FTP et MAIL.

    Poste Client : Station Windows pour l'administration et les tests de flux.

Plan d'adressage (Exemple Compagnie E / n°5)

    Interface IN : 192.168.5.254/24

    Interface DMZ : 172.16.5.254/24

    Interface OUT : 192.36.253.50/24

    Réseau Interne : 192.168.5.0/24

📝 Sommaire des Travaux Pratiques

[Lab 1] Prise en main et Maintenance

    -Initialisation du firewall et accès à l'interface d'administration Web (https://10.0.0.254/admin).

    -Configuration des préférences (délai d'inactivité illimité).

    -Paramétrage système : langue (Français), clavier, fuseau horaire et activation du service SSH.

    -Gestion des licences et mise en place de la sauvegarde automatique hebdomadaire avec mot de passe.

    -Sécurisation du compte admin.

[Lab 2] Gestion des Objets

    Création d'une base d'objets structurée :

        -Machines : Firewalls distants (Fw_A, Fw_B, etc.) et serveurs internes.

        -Réseaux : LAN distants (Lan_in_A, Lan_in_B, etc.).

        -Services : Création d'un service TCP personnalisé pour le webmail (port 808).

    Organisation en Groupes d'objets (ex: groupe Serveurs regroupant DNS, WEB, FTP, MAIL).

[Lab 3] Configuration Réseau & Interfaces

    -Configuration des interfaces physiques (Ethernet0 à Ethernet4).

    -Attribution des adresses IP statiques sur les interfaces IN, OUT et DMZ1.

    -Configuration de la station de travail (IP, Masque, Passerelle et DNS).

[Lab 4] Routage Statique

    -Configuration de la Passerelle par défaut (Gateway formateur : 192.36.253.254).

    -Mise en place de routes statiques vers les réseaux internes des autres entreprises via leurs firewalls respectifs.

    -Tests de connectivité ICMP (ping) inter-sites.

[Lab 5] Translation d'adresses (NAT)

    -Mise en place du Masquerading (NAT dynamique) pour l'accès à Internet.

    -Configuration de NAT Statique (Bimap) pour publier les serveurs FTP et MAIL avec des IP publiques dédiées.

    -Redirection de port (PAT) pour rendre le serveur WEB joignable sur l'IP publique du firewall.

[Lab 6] Filtrage (Security Policy)

    Élaboration d'une politique de sécurité granulaire :

        -Sortant : Autorisation HTTP/HTTPS (avec blocage par géolocalisation pour la Corée du Sud et blocage FQDN pour cnn.com).

        -Accès stagiaire : Restriction spécifique du protocole FTP pour une IP donnée.

        -Administration : Autorisation du SSH uniquement vers les firewalls voisins.

        -Entrant : Publication sécurisée des services avec traçage des logs et levée d'alarmes majeures pour les accès à l'interface d'administration.

🏁 Conclusion

Ce dépôt constitue un kit complet pour toute personne souhaitant s'entraîner sérieusement à l'administration des solutions Stormshield. Vous y trouverez :

    -Le Sujet du Lab : L'énoncé détaillé des exercices et le cahier des charges technique.

    -Le Compte Rendu : Ma documentation pas-à-pas incluant les captures d'écran, les vérifications de flux (ping, telnet, ftp) et les explications des configurations choisies.

    -Les Machines Virtuelles (VM) : Les environnements (SNS EVA, serveur Debian) entièrement configurés selon les exercices décrits.
