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
