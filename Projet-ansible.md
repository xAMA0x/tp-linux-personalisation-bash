Vous devez créer un projet d’automatisation avec Ansible.

Vous devez  choisir librement un projet d'infrastructure (réseaux, système, ou autre) à automatiser, à condition qu'il respecte les critères de sécurité et de gestion d'un environnement Linux.

## Objectifs du Projet

- **👏 5 POINTS 👏**  
  Créer un projet utile, réutilisable dans la vie courante ou potentiellement utile dans un cadre professionnel.

- **👏 5 POINTS 👏**  
  Apprendre à déployer et automatiser pour garantir une configuration cohérente et rapide.


### Exemples de Projets

- **Installation de Docker** : Gestion de conteneurs pour déployer des applications dans des environnements isolés.
- **Mise en place d’un WAF (ModSecurity)** : Sécuriser les applications contre les attaques web courantes.
- **Configuration de certificats SSL (OpenSSL)** : Chiffrer les connexions réseau.
- **Déploiement d’un service de partage de fichiers (PsiTransfer)** : Transfert de données sécurisé.
- **Services de gestion (OpenMediaVault)** : Accès centralisé aux données.

Les étudiants doivent utiliser **Ansible** pour automatiser chaque étape de leur projet, incluant la configuration SSH sécurisée jusqu’à l'installation et l'activation des services choisis.

---

## Modalités de Présentation

- **Durée** : 10 minutes maximum par groupe de 2/3 personnes.
- **Supports visuels** : Les slides ne sont pas obligatoires, mais peuvent être utilisés si souhaité.
- **Structure recommandée** : Introduction, description de l’architecture, démonstration de l’automatisation, aspects de sécurité, tests et conclusion.

---

## Évaluation

Chaque groupe sera noté selon la grille suivante, basée sur la qualité de la présentation orale et de la démonstration.

### Grille de notation

| Catégorie                    | Critères                                                                                                                                                                                                                                            | Points |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| **Architecture de l’Infrastructure** | Présence d’un diagramme clair de l'architecture et bonne organisation des composants. Explication de l’architecture réseau, des ports et des règles de pare-feu.                                                                                               | 5      |
| **Automatisation avec Ansible**     | Explication des playbooks et de leur structure. Utilisation efficace des rôles Ansible pour modulariser chaque composant. Cohérence et clarté des tâches automatisées.                                                                      | 5      |
| **Aspects Sécurité**                | Bonne gestion des accès SSH et mise en place de clés de sécurité. Protection adéquate de l'application avec WAF. Application et validation de certificats SSL. Sécurisation des fichiers et services (permissions, accès).                       | 5      |
| **Démo**                            | Présentation de l'automatisation du déploiement de l’infrastructure sur une VM fournie par l'intervenant (Sébastien B.) : 4 VCPU, 8 Go RAM, 100 Go SSD, Debian 12, utilisateur `ansible` avec sudoers sans mot de passe.                       | 5      |
| **Bonus**                           | Le projet est prouvé utile et réutilisable dans un contexte personnel ou professionnel, ou ouvert en open source sur GitHub.                                                                                                                   | 5      |

---
