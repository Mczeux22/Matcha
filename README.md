# Plan d'action pour le projet Web Matcha (Django)

## ✨ Objectif

Construire un site de rencontres web avec les fonctionnalités demandées dans le sujet "Web Matcha" en utilisant Django (Python), HTML/CSS et JS minimal (si nécessaire).

---

## 1. 🔧 Mise en place de l'environnement

### 1.1. Créer le dossier de projet

```bash
mkdir matcha && cd matcha
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate sur Windows
```

### 1.2. Installer Django

```bash
pip install django
echo "Django>=4.2" > requirements.txt
```

### 1.3. Démarrer le projet Django

```bash
django-admin startproject config .
python manage.py startapp users
python manage.py startapp core
```

---

## 2. 📂 Structure du projet

```
matcha/
├── config/               # Configuration du projet Django
├── core/                 # App principale (recherche, profils, chat...)
├── users/                # Gestion des utilisateurs
├── templates/            # Fichiers HTML (Jinja2)
├── static/               # CSS / JS / images
├── media/                # Photos utilisateurs (upload)
├── requirements.txt
└── .env                  # Variables sensibles (ne pas push)
```

---

## 3. ⚖️ Base de données

Modélisation avec Django ORM :

* Utilisateur (modèle personnalisé `AbstractUser`)
* Profil (bio, orientation, tags, photos, location, fame\_rating)
* Tags
* Likes / Blocks / Reports
* ChatMessages
* Notifications
* Visites

---

## 4. ⚡ Fonctionnalités (par étape)

### 4.1 Authentification & Inscription

* Email, pseudo, nom, prénom, mot de passe fort
* Email de vérification avec lien unique
* Connexion / déconnexion / réinitialisation

### 4.2 Gestion du profil

* Création / modification du profil
* Photos (max 5)
* Tags (recyclables)
* Système de localisation (auto + manuel)
* Fame rating (nombre de likes, vues, interactions)

### 4.3 Matching & recherche

* Liste de suggestions filtrables
* Critères : orientation, distance, tags, popularité
* Recherche avancée (filtres multiples)

### 4.4 Vue de profil & interactions

* Vue détaillée des autres profils (sauf email/mdp)
* Like, unlike, block, report
* Voir qui nous a liké / visité
* Online / dernière connexion

### 4.5 Chat

* Seulement entre profils connectés (like mutuel)
* Temps réel (WebSocket ou long polling avec Ajax)

### 4.6 Notifications

* Temps réel (like, message, vue, unlike)
* Visible depuis toutes les pages

---

## 5. 🌐 Front-end

* Templates HTML avec `templates/`
* CSS dans `static/css/`
* JavaScript (minimal ou WebSocket pour le chat)
* Design responsive mobile-friendly

---

## 6. 👁️ Sécurité & validation

* Aucune info sensible en dur (utiliser `.env`)
* Formulaires validés (Django Forms)
* Protection CSRF, XSS, SQLi (intégrées dans Django)
* Uploads contrôlés (taille/type)

---

## 7. ✨ Bonus (seulement si tout le reste est 100% stable)

* Authentification sociale (Google, Facebook...)
* Carte interactive (Leaflet + GPS)
* Vidéo / audio chat (WebRTC)
* Planificateur de rendez-vous

---

## 8. 📄 Remise

* Projet dans un repo Git propre
* `.env` dans `.gitignore`
* Pas d'erreur, warning, fail de sécurité
* Minimum 500 profils en base

---

## 📊 Conseils

* Tester chaque étape avant de passer à la suivante
* Sauvegarder régulièrement dans Git
* Créer un fichier `checklist.md` pour cocher les fonctionnalités faites

Tu peux maintenant passer à l'étape 1 ! 🚀
