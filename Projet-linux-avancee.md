## 🚀 Introduction aux Mini-Projets Pratiques d'Administration Linux Avancée

Bienvenue dans ce TP avancé d'administration Linux ! Vous allez réaliser une série de mini-projets concrets et pratiques, conçus spécialement pour renforcer vos compétences en gestion d'infrastructures sous Linux. Vous aurez l'occasion d'approfondir vos connaissances techniques en automatisant des infrastructures modernes, tout en découvrant des outils incontournables dans le monde professionnel.

### 🎯 Objectifs pédagogiques :
- Renforcer vos compétences en administration Linux avancée.
- Apprendre à utiliser Docker Compose pour automatiser entièrement la mise en place d'infrastructures complètes.
- Découvrir et maîtriser des outils professionnels largement utilisés dans l'industrie informatique (Ansible, Prometheus, Grafana, ELK, OpenVPN, etc.).
- Développer vos capacités d'autonomie, de recherche et de résolution de problèmes techniques.

### 📌 Déroulement du TP :
Parmi les **16 mini projets proposés**, vous devez en sélectionner **3** qui vous intéressent particulièrement. Vous devrez ensuite concevoir une infrastructure complète en utilisant **Docker Compose**, permettant de déployer automatiquement et simultanément vos trois projets choisis.

Votre travail consistera à :
- Élaborer un fichier `docker-compose.yml` clair et documenté.
- Tester le bon fonctionnement de l'infrastructure complète.
- Rédiger une courte documentation expliquant vos choix techniques et vos difficultés éventuelles.

## 📌 **Critères d'évaluation :**
Chaque projet choisi devra être accompagné d'un dossier expliquant clairement :

- Un schéma simplifié de l'infrastructure Docker Compose.
- Un fichier `docker-compose.yml` propre et documenté.
- Une documentation simple expliquant les étapes réalisées.
- Les scripts ou configurations personnalisées éventuels (clairs et commentés).

---

### **1. Serveur web sécurisé (Apache ou Nginx)**  
- Dockerisation complète d’un serveur web (Apache/Nginx).
- Gestion automatisée des certificats SSL avec Let's Encrypt (via Certbot).
- Page web statique simple à afficher pour démontrer la sécurisation.

---

### **2. Surveillance avancée avec Prometheus & Grafana**  
- Containeriser Prometheus et Grafana.
- Collecter les métriques système (CPU, RAM, disque, réseau) via Node Exporter.
- Créer des dashboards Grafana clairs pour afficher les données collectées.
- Ajouter quelques alertes simples (exemple : utilisation CPU > 80%).

---

### **3. Déploiement automatique avec Ansible**  
- Dockeriser Ansible avec une image dédiée.
- Prévoir un scénario simple mais concret (exemple : installation automatique de WordPress ou autre).
- Ansible doit configurer une ou plusieurs cibles Docker.

---

### **4. Serveur mail sécurisé complet (Postfix/Dovecot)**  
- Dockeriser un serveur mail complet (Postfix, Dovecot, antispam).
- Ajouter SSL et gestion de comptes mail virtuels.
- Tester avec Roundcube ou équivalent pour l'interface utilisateur.

---

### **5. Infrastructure multi-container applicative (Docker Compose)**  
- Stack applicative (exemple : LAMP, WordPress, Nextcloud).
- Séparation claire des services (DB, App, Frontend).
- Automatiser sauvegarde/restauration des données (volumes Docker).

---

### **6. Serveur VPN sécurisé (OpenVPN/WireGuard)**  
- Containeriser OpenVPN ou WireGuard.
- Automatisation de la génération des clés et gestion utilisateurs.
- Configuration firewall basique intégrée au container.

---

### **7. Serveur de sauvegarde automatisé (Rsync/BorgBackup)**  
- Dockeriser un serveur de sauvegarde (ex: BorgBackup ou Rsync).
- Script d’automatisation via cron intégré dans un container.
- Gérer des restaurations via un script simple et clair.

---

### **8. Gestion centralisée de logs (ELK Stack)**  
- Installation de Elasticsearch, Logstash, Kibana via Docker Compose.
- Centraliser les logs système (syslog Dockerisé).
- Visualisation des logs par Kibana avec dashboards simples préconfigurés.

---

### **9. Serveur FTP sécurisé et automatisé (vsftpd)**  
- Dockerisation complète d’un serveur FTP (vsftpd).
- Automatisation et gestion des utilisateurs virtuels.
- Configuration SSL/TLS complète.

---

### **10. Système de ticketing (GLPI)**  
- Dockeriser un serveur GLPI avec base de données (MySQL/MariaDB).
- Mise en place d'authentification LDAP/locale simplifiée (facultatif LDAP).
- Fonctionnement complet : création, gestion, et suivi d'incidents.

---

### **11. Infrastructure multimédia & gestion de torrents (Radarr, Sonarr, Transmission, Plex)**  
- Déploiement Docker de Radarr et Sonarr pour gérer les films et séries.
- Transmission ou Deluge comme client torrent intégré.
- Plex ou Jellyfin pour le streaming multimédia.
- Configuration automatique de volumes persistants pour stockage multimédia.

---

## 12. Serveur DNS avancé avec Bind (chroot et DNSSEC)

### Objectif principal
Déployer et configurer un serveur DNS Bind sécurisé dans un environnement chrooté, tout en mettant en place **DNSSEC** pour garantir l’intégrité et l’authenticité des réponses DNS.

### Points clés à implémenter
1. **Installation et configuration de Bind** :  
   - Création de zones directes et inverses.  
   - Configuration de Bind pour tourner en environnement chroot (répertoires, liens symboliques, etc.).
2. **Gestion de la sécurité** :  
   - Paramétrage de DNSSEC (génération des clefs, signature de zone).  
   - Configuration des ACL (Listes de contrôle d’accès) pour limiter la récursion à un réseau local ou une IP spécifique.  
3. **Test de résolution** :  
   - Utiliser des commandes telles que `dig` ou `nslookup` pour vérifier la signature DNSSEC et la résolution interne/externe.
4. **Documentation** :  
   - Schéma de l’infrastructure DNS.  
   - Étapes de mise en place de la chroot.  
   - Explication du processus de signature DNSSEC.

### Résultat attendu
Un serveur DNS fonctionnel, sécuritaire, avec **DNSSEC** activé, fournissant des réponses vérifiables via un test local ou externe.

---

## 13. Hébergement de services web sécurisés avec Apache + Proxy inverse Nginx

### Objectif principal
Combiner Apache et Nginx pour servir plusieurs sites web, mettre en place un **proxy inverse** et chiffrer les connexions grâce à des certificats TLS (Let's Encrypt ou auto-signés).

### Points clés à implémenter
1. **Déploiement multi-conteneurs** :  
   - Un conteneur pour Nginx (en proxy inverse, gérant les connexions HTTPS).  
   - Un conteneur pour Apache (serveur web principal).  
2. **Virtual Hosts / Configuration multi-sites** :  
   - Héberger au moins deux sites web distincts (ex. site1.domain.tld et site2.domain.tld).  
   - Mettre en place le SNI (Server Name Indication) pour la gestion des certificats multiples.
3. **Sécurisation** :  
   - Génération et renouvellement (automatisé si possible) de certificats TLS via Let’s Encrypt.  
   - Mise en place de redirections HTTP -> HTTPS.  
   - Configuration d’entêtes de sécurité (HSTS, X-Frame-Options, etc.).
4. **Monitoring des logs** :  
   - Activer les logs d’accès et d’erreurs sur Apache et Nginx.  
   - Mettre en place de simples alertes ou un script de parsing de logs pour détecter des comportements suspects (ex. Fail2ban).
5. **Documentation** :  
   - Décrire le flux de connexion (client -> Nginx -> Apache).  
   - Expliquer les différents fichiers de configuration.

### Résultat attendu
Une stack web sécurisée, capable d’héberger plusieurs sites avec un proxy inverse Nginx en HTTPS.

---

## 14. Partage de fichiers : Mise en place d’un serveur Samba + NFS

### Objectif principal
Concevoir une plateforme de partage de fichiers qui réponde aux environnements **Windows** (Samba) et **Linux/Unix** (NFS) avec un minimum de sécurité.

### Points clés à implémenter
1. **Serveur Samba** :  
   - Configuration de partages samba pour différents groupes/utilisateurs.  
   - Gestion d’un annuaire d’utilisateurs local ou via un backend (tdbsam ou LDAP pour les plus avancés).  
   - Mise en place d’une authentification sécurisée (SMB version >=3, protocoles de chiffrement).
2. **NFS** :  
   - Exportation de répertoires pour clients Linux/Unix.  
   - Configuration d’autorisations d’accès basées sur les adresses IP ou le DNS.  
3. **Sécurité et isolation** :  
   - Docker ou VM dédiés pour chaque service, ou un conteneur unique avec Samba et NFS configurés sur deux interfaces différentes (selon les bonnes pratiques).  
   - Vérification du firewall (ou iptables) pour n’autoriser que l’accès depuis le réseau local.
4. **Tests de montée en charge** :  
   - Mesurer les performances (I/O, latences) via des outils comme `dd`, `ioping`, etc.  
   - Optionnel : mise en place d’une petite routine de surveillance (ex. script bash) pour alerter en cas de forte utilisation.
5. **Documentation** :  
   - Structure des répertoires partagés.  
   - Modalités d’accès selon le système client (Windows/Linux).  
   - Fichiers de configuration (smb.conf, /etc/exports…).

### Résultat attendu
Un serveur de partage de fichiers pour différents systèmes, avec une gestion fine des droits et la sécurisation de base.

---

## 15. Gestion de clients réseau via DHCP/LDAP (Network Client Management)

### Objectif principal
Installer et configurer un serveur DHCP pour attribuer dynamiquement des adresses IP, puis intégrer une solution d’authentification centralisée via **OpenLDAP**.

### Points clés à implémenter
1. **Serveur DHCP** :  
   - Configuration du service (ex. ISC DHCP Server) pour gérer un pool d’adresses IP.  
   - Réservation d’adresses pour certains clients (identification par adresse MAC).
2. **Serveur LDAP** :  
   - Mise en place d’OpenLDAP (structure d’arborescence, schéma minimal).  
   - Création d’utilisateurs, groupes et attributs de base pour la gestion.  
3. **Authentification centralisée** :  
   - Configurer un client Linux pour s’authentifier via LDAP (PAM, NSS).  
   - Optionnel : intégrer Samba ou NFS pour que les utilisateurs LDAP aient accès à un home directory partagé.
4. **Sécurisation** :  
   - Activer le chiffrement TLS dans LDAP (ldaps://) pour protéger les identifiants.  
   - Restreindre l’accès DHCP/LDAP aux réseaux internes uniquement.
5. **Documentation** :  
   - Décrire le plan d’adressage du DHCP.  
   - Expliquer la configuration PAM/NSS pour la connexion d’utilisateurs LDAP.

### Résultat attendu
Un système d’attribution IP dynamique (DHCP) et d’authentification centralisée (LDAP) fonctionnel, démontrant la gestion d’utilisateurs sur un réseau Linux.

---

## 16. Services de messagerie et sécurité des e-mails (Postfix, Dovecot, SPF, DKIM, DMARC)

### Objectif principal
Déployer une architecture mail complète intégrant **Postfix** pour l’envoi, **Dovecot** pour la réception (IMAP/POP3), et ajouter des mécanismes de sécurité comme SPF, DKIM et DMARC.

### Points clés à implémenter
1. **Serveur Postfix** :  
   - Configuration de la file d’attente, des hôtes de confiance.  
   - Fichier `main.cf` et `master.cf` paramétrés pour supporter SSL/TLS.
2. **Serveur Dovecot** :  
   - Configuration des protocoles IMAP et/ou POP3.  
   - Gestion d’utilisateurs locaux (fichiers passwd) ou via LDAP (optionnel).  
   - Mise en place du chiffrement TLS pour l’accès mail.
3. **SPF, DKIM, DMARC** :  
   - Déploiement d’un outil de signature DKIM (opendkim).  
   - Configuration DNS des enregistrements SPF, DKIM et DMARC.  
   - Tests de vérification d’intégrité des e-mails envoyés et reçus.
4. **Tests et sécurité** :  
   - Vérifier l’envoi/réception à partir d’un webmail ou d’un client mail (Thunderbird, par exemple).  
   - Activer un service anti-spam (ex. SpamAssassin) pour bonus.  
   - Suivre les logs pour détecter d’éventuelles tentatives de relais non autorisées.
5. **Documentation** :  
   - Explication du flux d’envoi et de réception.  
   - Captures d’écran ou retour de commandes prouvant le bon fonctionnement (test SPF, DKIM).  
   - Configurations DNS et extraits de fichiers Postfix/Dovecot.

### Résultat attendu
Une plateforme de messagerie complète et sécurisée, conforme aux standards d’authentification SPF/DKIM/DMARC, apte à envoyer et recevoir des e-mails de manière fiable.
