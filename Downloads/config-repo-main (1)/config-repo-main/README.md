# Config Repository - E-Commerce Microservices

Ce dépôt contient les configurations centralisées pour l'application e-commerce basée sur une architecture microservices.

## 📁 Fichiers de Configuration

### Services Métier

- **produits-service.yml** : Configuration du microservice de gestion des produits
  - Base de données MySQL : `db_produits`
  - Port : 9001

- **commandes-service.yml** : Configuration du microservice de gestion des commandes
  - Base de données MySQL : `db_commandes`
  - Port : 9002
  - Propriété personnalisée : `mes-config-ms-commandes-last: 10` (nombre de jours pour les dernières commandes)

### Services d'Infrastructure

- **gateway.yml** : Configuration de l'API Gateway
  - Port : 8080
  - Routes configurées pour tous les microservices
  - Filtres de logging activés

- **interface-service.yml** : Configuration du service interface (Front API)
  - Port : 9003
  - Configuration JWT pour l'authentification

- **application.yml** : Configuration générale du Config Server

## 🔧 Utilisation

Ce dépôt est utilisé par le **Spring Cloud Config Server** pour centraliser toutes les configurations des microservices.

Le Config Server récupère automatiquement ces configurations depuis ce dépôt Git lors du démarrage.

## 📝 Notes

- Les configurations sont versionnées et suivies via Git
- Toute modification nécessite un commit et un push vers ce dépôt
- Les services peuvent recharger leur configuration via l'endpoint `/actuator/refresh` (si activé)
