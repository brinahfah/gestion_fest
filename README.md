# echeance_fest

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

# GestionFest – Version 1.0

## Présentation

GestionFest est une application Flutter développée pour le suivi des étudiants de BTS.

L'application permet à un référent de :

* gérer les élèves ;
* consulter et compléter les missions ;
* suivre les rendez-vous ;
* ajouter des commentaires ;
* enregistrer les informations dans Firebase.

Une automatisation des notifications par e-mail est disponible dans un dépôt GitHub séparé : **email-automation**.

---

## Technologies utilisées

* Flutter
* Dart
* Firebase Authentication
* Cloud Firestore

---

## Structure du projet

```text
lib/
 ├── models/
 ├── pages/
 ├── widgets/
 └── main.dart
```

---

## Installation

### 1. Cloner le projet

```bash
git clone https://github.com/brinahfah/gestion_fest.git
```

### 2. Installer les dépendances

```bash
flutter pub get
```

### 3. Configurer Firebase

Le projet utilise Firebase.

Ajouter les fichiers de configuration Firebase correspondant au projet :

* Android : `android/app/google-services.json`
* iOS : `ios/Runner/GoogleService-Info.plist`

Configurer également `firebase_options.dart` si nécessaire.

### 4. Lancer l'application

```bash
flutter run
```

---

## Base de données Firestore

Les principales collections sont :

* `eleves`
* `missions`
* `meets`
* `referent`
* `tuteurs`
* `deadlines`

---

## Fonctionnalités disponibles (Version 1)

* Authentification Firebase
* Gestion des élèves
* Gestion des missions
* Gestion des rendez-vous
* Calcul automatique du statut des missions et rendez-vous
* Enregistrement des commentaires
* Stockage des données dans Firestore

---

## Notifications

Les notifications automatiques par e-mail ne sont pas incluses dans ce dépôt.

Elles sont développées dans le dépôt :

`email-automation`

---

## Évolutions prévues

* Amélioration de l'interface utilisateur
* Gestion de plusieurs référents
* Notifications Push Firebase Cloud Messaging
* Tableau de bord administrateur
* Statistiques et rapports
* Interface administrateur
---

## Auteur

Développé dans le cadre du projet GestionFest – Version 1.0.

# Email Automation – Version 1.0

## Présentation

Ce projet est un service Node.js permettant d'envoyer automatiquement des e-mails de rappel aux référents en fonction des échéances enregistrées dans Cloud Firestore.

Il complète l'application Flutter **GestionFest** et s'exécute automatiquement grâce à GitHub Actions.

---

## Technologies utilisées

* Node.js
* Firebase Admin SDK
* Cloud Firestore
* SendGrid
* GitHub Actions

---

## Fonctionnement

Le script :

1. se connecte à Firestore ;
2. récupère les échéances enregistrées dans la collection `deadlines` ;
3. calcule les notifications à envoyer (J-7, Jour J, J+7) ;
4. récupère l'adresse e-mail du référent ;
5. envoie un e-mail via SendGrid ;
6. enregistre dans Firestore les notifications déjà envoyées afin d'éviter les doublons.

---

## Installation

### Installer les dépendances

```bash
npm install
```

---

## Configuration

Le projet utilise des **GitHub Secrets**.

Les secrets suivants doivent être configurés dans le dépôt GitHub :

* `SENDGRID_KEY`
* `SENDGRID_EMAIL`
* `FIREBASE_SERVICE_ACCOUNT`

Aucune clé ou fichier de configuration sensible n'est stocké dans le dépôt.

---

## GitHub Actions

Le workflow situé dans :

```text
.github/workflows/email.yml
```

exécute automatiquement le script selon la planification définie.

---

## Collections Firestore utilisées

* `deadlines`
* `referent`
* `missions`
* `meets`

---

## Notifications gérées (Version 1)

* Rappel à J-7
* Notification le Jour J
* Relance à J+7 (si nécessaire)

Les notifications sont envoyées par e-mail au référent.

---

## Dépôt associé

L'application Flutter est disponible dans un dépôt séparé :

**gestion_fest**

---

## Évolutions prévues (Version 2)

* Prise en charge de plusieurs référents
* Templates HTML SendGrid
* Personnalisation des e-mails (nom du référent, élève, mission, rendez-vous)
* Journalisation des envois
* Gestion avancée des rappels

---

## Auteur

Développé dans le cadre du projet GestionFest – Version 1.0.
