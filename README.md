# Système de Gestion des Commandes de Ciments

Une application web Symfony pour la gestion des commandes de ciments, des stocks, et des clients.

## Fonctionnalités

- Gestion des stocks de ciment
- Gestion des clients
- Gestion des commandes
- Tableau de bord avec statistiques
- Système d'authentification sécurisé
- Interface responsive avec Tailwind CSS

## Prérequis

- PHP 8.1 ou supérieur
- Composer
- SQLite3

## Installation

1. Décompressez l'archive:
```bash
unzip cement-orders.zip
cd cement-orders
```

2. Installer les dépendances PHP :
```bash
composer install
```

3. Créer la base de données et appliquer les migrations :
```bash
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate
```

4. Créer l'utilisateur administrateur :
```bash
php bin/console app:create-admin
```
Cela créera un utilisateur admin avec les identifiants suivants :
- Email : admin@example.com
- Mot de passe : admin123

5. Lancer le serveur de développement :
```bash
php -S localhost:8000 -t public/
```

## Structure du Projet

- `src/Entity/` : Entités Doctrine (User, Stock, Client, Order, OrderItem)
- `src/Controller/` : Contrôleurs de l'application
- `src/Form/` : Types de formulaires
- `src/Repository/` : Repositories Doctrine
- `templates/` : Templates Twig
- `config/` : Fichiers de configuration

## Utilisation

1. Accéder à l'application via : `http://localhost:8000`
2. Se connecter avec les identifiants administrateur
3. Commencer par configurer les stocks de ciment
4. Ajouter des clients
5. Créer et gérer les commandes

## Fonctionnalités Principales

### Gestion des Stocks
- Ajout/modification/suppression de produits
- Suivi des quantités
- Alertes de stock bas
- Historique des mouvements

### Gestion des Clients
- Création de fiches clients
- Historique des commandes par client
- Coordonnées et informations de contact

### Gestion des Commandes
- Création de nouvelles commandes
- Suivi du statut des commandes
- Historique complet
- Calcul automatique des montants

### Tableau de Bord
- Vue d'ensemble des activités
- Statistiques des ventes
- Suivi des stocks
- Alertes et notifications

## Sécurité

- Authentification requise pour accéder à l'application
- Différents niveaux d'accès (ROLE_USER, ROLE_ADMIN)
- Protection CSRF sur les formulaires
- Validation des données

## Maintenance

Pour mettre à jour la base de données après des modifications d'entités :
```bash
php bin/console make:migration
php bin/console doctrine:migrations:migrate
```

## Support

Pour toute question ou problème, veuillez créer une issue dans le dépôt GitHub.

## Licence

Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus de détails.
