# Application de gestion de paris sportifs sur des matchs de football

## Présentation du projet

Ce projet collectif a été réalisé dans le cadre de ma formation de conceptrice développeuse d’applications.

L’objectif était de concevoir et de développer une application permettant de gérer des paris sportifs portant sur des matchs de football.

Ce projet m'a permis de mettre en pratique les compétences acquises en conception et développement d’une application, en gestion de base de données et en travail collaboratif.

## Objectifs du projet

- Concevoir une application répondant à un besoin fonctionnel défini
- Organiser et gérer les données relatives aux matchs, aux clubs, aux utilisateurs et aux paris
- Mettre en oeuvre une architecture applicative adaptée
- Collaborer en équipe tout au long du développement

## Fonctionnalités principales

- Gestion des matchs de football
- Gestion des clubs de football
- Gestion des utilisateurs
- Consultation des résultats des matchs
- Gestion des paris sportifs

## Technologies utilisées

- Langage backend : Java
- Framework backend : Spring Boot
- Sécurité : Spring security
- Frontend : HTML5, CSS3, TypeScript
- Framework frontend : Angular
- Bibliothèque CSS : Bootstrap 5
- Base de données : MySQL
- Environnement local : MAMP
- Gestion de versions : Git et Gitlab

### Conception fonctionnelle et technique

Avant le développement, nous avons réalisé plusieurs travaux de conception :

- Élaboration du MCD (Modèle Conceptuel de Données) et du MLD (Modèle Logique de Données) à l'aide de draw.io.
- Réalisation d'une maquette de l'application avec draw.io.
- Définition d'une architecture organisée autour de trois API :
  - **API Match :** gestion des matchs de football et des clubs
  - **API Paris :** gestion des paris et des relations avec les utilisateurs
  - **API Front :** partie dédiée à l'interface utilisateur
- Mise en place de deux bases de données MySQL distinctes, associées aux deux API backend : Match et Paris.

### Organisation du développement

Le projet a été réalisé en équipe selon une organisation agile comprenant trois sprints. Les fonctionnalités à développer étaient définies sous forme de user stories dans GitLab. Chaque membre de l'équipe prenait en charge différentes tâches en fonction des priorités et des objectifs de chaque sprint.

Git et GitLab ont été utilisés pour la gestion de versions et le suivi du travail collaboratif.


### Travail collaboratif

Le développement a été organisé autour des user stories et des objectifs de chaque sprint. GitLab a été utilisé pour organiser et suivre les tâches du projet ainsi que pour la gestion de versions avec Git.

## Architecture de l'application

### Architecture générale : trois tiers

L'application reposait sur une architecture en trois couches :

- **Couche présentation :** interface utilisateur, formulaires, navigation et appels HTTP vers les API.
- **Couche logique applicative :** règles métier, traitements, validations et exposition des endpoints REST.
- **Couche données :** stockage dans les bases de données MySQL, gestion des tables et des relations, accès aux données via JPA/Hibernate.

### Architecture applicative : découpage en services

Le backend était organisé autour de deux API :

- **API Match :** gestion des matchs de football et des clubs.
- **API Paris :** gestion des paris et des utilisateurs.

Chaque API backend disposait de sa propre base de données MySQL.

### Communication entre les API

Les deux API communiquaient par requêtes HTTP grâce à `WebClient`.

L'API Paris utilisait notamment l'identifiant d'un match géré par l'API Match afin de relier un pari à la rencontre correspondante. Cet identifiant était également enregistré dans la base de données de l'API Paris.

### Outils de conception et organisation

- **Conception des données :** MCD et MLD réalisés avec draw.io.
- **Maquettage :** draw.io.
- **Gestion des tâches :** user stories organisées dans GitLab.
- **Méthode de travail :** trois sprints successifs.
- **Gestion de versions :** Git et GitLab.

## Ma contribution personnelle

Dans le cadre de ce projet collectif, j'ai principalement contribué au développement de l'API Match avec Java et Spring Boot. Mes travaux ont porté sur la gestion des matchs, les opérations de consultation, les tests unitaires sur certaines fonctionnalités de l'API Clubs et la sécurisation des endpoints.

### 1. Développement de l'API Match

- Création de l'entité `Match` et des composants associés : repository, service et controller.
- Mise en place de la gestion des rencontres avec une énumération (`enum`) permettant de distinguer les rôles des clubs : domicile et extérieur.
- Développement de la création d'un match avec sa date, son club à domicile et son club à l'extérieur.
- Implémentation des fonctionnalités `getById` et `getAllMatch` pour consulter un match par son identifiant ou récupérer la liste des matchs.
- Mise à jour des services et des controllers associés.
- Restriction de la mise à jour du nombre de buts aux utilisateurs disposant du rôle administrateur.

### 2. Participation à l'API Clubs

- Développement des fonctionnalités `getById` et `getAll` pour consulter un club par son identifiant ou récupérer la liste des clubs.
- Mise à jour de `ClubController` et du service associé.
- Réalisation des tests unitaires associés à ces fonctionnalités.

### 3. Sécurisation des API avec Spring Security et JWT

Participation à la mise en place de la sécurité de l'API Match, notamment :

- Configuration de Spring Security et des règles d'accès selon les rôles utilisateurs.
- Mise à jour de `ClubController` et `MatchController` pour prendre en compte l'authentification et les autorisations.
- Intégration de l'authentification par jetons JWT (*JSON Web Token*).
- Mise en place et configuration des composants de sécurité :
  - `JwtAuthenticationFilter.java` : filtre d'authentification JWT.
  - `JwtUtil.java` : utilitaires liés aux jetons JWT.
  - `SecurityConfig.java` : configuration de Spring Security.
  - `CorsConfig` : configuration des échanges entre origines différentes.
- Configuration des paramètres JWT dans `application.properties`, notamment le secret et la durée d'expiration des jetons.

### Compétences mises en pratique

Java, Spring Boot, conception d'API REST, architecture en couches, JPA/Hibernate, MySQL, Spring Security, JWT, gestion des rôles, tests unitaires, Git et GitLab.

## Contexte

Projet collectif réalisé durant ma formation de conceptrice développeuse d’applications (titre professionnel de niveau 6).
