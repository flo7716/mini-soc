# mini-soc

# 🛡️ Mini-SOC – Security Operations Center personnel

## 📌 Présentation

Ce projet est un **mini-SOC (Security Operations Center)** développé **entièrement par mes propres soins**, dans un objectif pédagogique et professionnel.

Il vise à reproduire, à échelle réduite, le fonctionnement d’un SOC réel :

* collecte de logs,
* détection d’événements de sécurité,
* génération d’alertes,
* notification automatique par email,
* supervision via un dashboard.

Ce projet permet de démontrer des compétences en **cybersécurité défensive**, **développement backend**, **automatisation** et **architecture SOC**.

---

## 🎯 Objectifs du projet

* Comprendre et implémenter une chaîne SOC complète
* Détecter des comportements suspects à partir de logs
* Centraliser et corréler les événements de sécurité
* Alerter automatiquement les utilisateurs et administrateurs
* Fournir une interface de supervision claire

---

## 🧱 Architecture globale

```
[Machine surveillée]
        |
        v
[Agent de collecte]
        |
        v
[Serveur Mini-SOC]
 ├─ API REST
 ├─ Moteur de détection
 ├─ Base de données
 ├─ Gestion des alertes
 ├─ Notifications email
 └─ Dashboard Web
```

---

## ⚙️ Composants principaux

### 🖥️ Agent de collecte

* Déployé sur les machines surveillées
* Lecture des logs système et applicatifs
* Normalisation des événements
* Envoi sécurisé vers le serveur SOC

Exemples de logs surveillés :

* Authentification SSH
* Connexions utilisateur
* Accès à des fichiers sensibles

---

### 🧠 Serveur Mini-SOC

* Réception des événements via API REST
* Analyse et corrélation des logs
* Application de règles de détection
* Génération d’alertes de sécurité

---

### 🚨 Moteur de détection

Basé sur des règles simples et compréhensibles :

* Seuils (ex: X échecs de connexion)
* Fenêtres temporelles
* Listes blanches / noires

Exemples :

* 5 échecs SSH en moins de 2 minutes
* Connexion depuis une IP inconnue
* Accès à un fichier critique hors horaires

---

### ✉️ Notifications email

* Envoi automatique lors d’une alerte
* Email contextualisé contenant :

  * type d’alerte
  * gravité
  * machine concernée
  * date et heure
  * recommandation

---

### 📊 Dashboard Web

* Vue centralisée des alertes
* Filtres par gravité, date et machine
* Historique des incidents
* Accès restreint par rôle (admin / utilisateur)

---

## 👥 Gestion des utilisateurs

* Comptes utilisateurs
* Rôles : Administrateur / Utilisateur
* Notifications ciblées par utilisateur
* Accès restreint aux alertes concernées

---

## 🧪 Scénarios de détection implémentés

* Brute force SSH
* Tentatives de connexion répétées
* Accès non autorisé à un fichier sensible
* Lancement de processus suspect

---

## 🛠️ Technologies utilisées

### Backend

* Python
* FastAPI / Flask
* SQLite / PostgreSQL

### Agent

* Python
* Envoi HTTP sécurisé

### Frontend

* HTML / CSS / JavaScript
* (Optionnel) React

### Notifications

* SMTP
* Serveur mail local (MailHog) ou Gmail

---

## 🚀 Installation rapide

```bash
git clone https://github.com/flo7716/mini-soc.git
cd mini-soc
```

Instructions détaillées disponibles dans chaque dossier (`agent/`, `server/`, `dashboard/`).

---

## 📁 Structure du dépôt

Voir l’arborescence complète dans la documentation du projet.

---

## 📚 Documentation

* Architecture : `docs/architecture.md`
* Règles de détection : `docs/detection-rules.md`
* Threat model : `docs/threat-model.md`
* API : `docs/api-spec.md`

---

## 🔒 Sécurité et limites

* Projet à but pédagogique
* Non destiné à un environnement de production
* Règles volontairement simples et explicables

---

## 📈 Évolutions possibles

* Intégration SIEM
* Notifications Slack / Telegram
* Ajout de corrélation avancée
* Tableau de bord temps réel

---

## 👤 Auteur

Projet développé par **[Florian André]**

---

## 📜 Licence

Ce projet est distribué sous licence MIT.
