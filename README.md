# LocalisationSmartphone – TP Mobile connecté

Application Android qui récupère la position GPS et l’envoie à un serveur PHP pour stockage dans MySQL.

## Fonctionnalités
- Obtention de la localisation (GPS / réseau)
- Affichage des coordonnées, altitude, précision
- Envoi automatique toutes les minutes (ou à chaque changement significatif)
- Stockage dans une base MySQL via une API REST (POST)
- Utilisation de **Volley** pour les requêtes HTTP
- Gestion des permissions Android (API 23+)

## Architecture
- **Client** : Android (Java, LocationManager, Volley)
- **Serveur** : PHP (orienté objet, PDO) + MySQL

## Installation

### 1. Backend
- Copier le dossier `localisation/` dans `htdocs` (XAMPP) ou `www` (WAMP)
- Importer le script SQL (création de la base et table `position`)
- Configurer la connexion MySQL dans `connexion/Connexion.php`
- Tester avec Postman ou un navigateur :  
  `POST http://localhost/localisation/createPosition.php`  
  avec paramètres `latitude`, `longitude`, `date_position`, `imei`

### 2. Android
- Ouvrir le projet dans Android Studio
- Modifier `SERVER_URL` dans `MainActivity.java` avec l’IP de votre PC
- Activer le mode développement et le débogage USB
- Lancer l’application

## Améliorations apportées
- Réponses JSON au lieu de texte brut
- Validation des données côté serveur
- Singleton Volley pour optimiser les requêtes
- Gération des erreurs HTTP
- Externalisation des chaînes
- Support des deux fournisseurs de localisation

## Prérequis
- Android Studio Hedgehog+
- JDK 11+
- Serveur local (XAMPP/WAMP) avec PHP 7.4+ et MySQL 5.7+
- Téléphone ou émulateur avec API 24+

## Licence
Projet pédagogique – libre d’utilisation.
