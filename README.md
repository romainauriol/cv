# 🚀 Homelab Infrastructure & Documentation

Bienvenue sur le dépôt de mon Homelab. Ce projet centralise le déploiement, l'administration et la supervision d'une infrastructure complète, conçue pour reproduire un environnement d'entreprise exigeant. 

L'objectif de ce dépôt est de documenter mes pratiques en tant que futur Administrateur Systèmes et Réseaux (TSSR), en mettant l'accent sur la sécurité, la haute disponibilité et l'automatisation.

---

## 🏗️ Architecture Globale

<div align="center">
  <!-- Remplacer les liens par tes futurs schémas réseau -->
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="image/schema_architecture_dark.png">
    <source media="(prefers-color-scheme: light)" srcset="image/schema_architecture_light.png">
    <img alt="Schéma de l'architecture réseau et système du Homelab" src="image/schema_architecture_light.png">
  </picture>
</div>

L'environnement repose sur une architecture virtualisée stricte, segmentée et sécurisée :

*   **Hyperviseur :** Nœuds sous **Proxmox VE** (Serveur physique Lenovo).
    *   *Optimisation :* Stockage SSD pour l'OS, HDD de 2 To en passthrough pour le stockage des données lourdes.
*   **Réseau & Sécurité :** Routeur/Pare-feu **pfSense** virtualisé.
    *   *Rôles :* Routage WAN/LAN, gestion fine du DHCP, segmentation réseau et filtrage.
*   **Système & Annuaire :** Contrôleur de Domaine sous **Windows Server 2022**.
    *   *Rôles :* Active Directory, DNS, gestion centralisée des clients Windows 11.

---

## 📚 Catalogue des Procédures et Déploiements

Chaque composant de ce Homelab fait l'objet d'une documentation détaillée expliquant le contexte, les prérequis, et les étapes de configuration.

### 🐳 Conteneurisation & Orchestration
*   **Docker & Portainer :** Déploiement sur VM Debian intégrée au cluster Proxmox. Gestion centralisée des conteneurs via l'interface Portainer.
    *   [📄 Consulter la procédure](docs/procedure_portainer.pdf)

### 🔐 Sécurité & Accès Distant
*   **OpenVPN & Authentification LDAP :** Sécurisation des accès distants avec pfSense et synchronisation des droits via l'annuaire Active Directory.
    *   [📄 Consulter la procédure](docs/Procedure_OpenVPN_LDAP.pdf)

### 📊 Supervision & Monitoring
*   **Zabbix :** Configuration d'un serveur de supervision, déploiement des agents et création d'alertes personnalisées.
    *   [📄 Consulter la procédure](docs/procedure_zabbix.pdf)
*   **Uptime Kuma :** Mise en place d'une solution de monitoring légère pour vérifier la disponibilité continue des services critiques.
    *   [📄 Consulter la procédure](docs/procedure_kuma.pdf)

### 💾 Haute Disponibilité & Sauvegardes
*   **Proxmox Backup Server (PBS) :** Déploiement de la solution de sauvegarde dédiée, gestion des datastores et déduplication.
    *   [📄 Consulter la procédure](docs/Procedure_proxmox_backup_server.pdf)
*   **Cluster Proxmox :** Configuration d'un nœud supplémentaire (pve02) et intégration de la stratégie de sauvegarde automatisée.
    *   [📄 Consulter la procédure](docs/Procedure_cluster_backup.pdf)

---

## 🚧 Projets en cours d'intégration

*   **ITSM Redmine :** Installation d'une solution de ticketing open-source en conteneur LXC (Proxmox), couplée à une intégration LDAP et résolution des problématiques de routage inter-VLAN. *(Procédure en cours de rédaction)*

---
*Maintenu par Romain Auriol - Déploiements et configurations réalisés dans le cadre de la certification TSSR.*
