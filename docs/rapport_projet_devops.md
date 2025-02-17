# Rapport de Projet DevOps

## Introduction
Ce rapport décrit la mise en œuvre d'une architecture d'application basée sur des microservices, en appliquant les principes DevOps. L'objectif est de garantir la portabilité, l'automatisation et la collaboration au sein de l'équipe tout au long du cycle de développement.

## Description de l'Application
L'application est composée de plusieurs microservices interconnectés, chacun ayant des responsabilités spécifiques :
- **Frontend** : Une application Next.js qui gère l'interface utilisateur, offrant une expérience utilisateur fluide et réactive.
- **API Gateway** : Un point d'entrée unique pour toutes les requêtes, gérant la communication entre les services et appliquant des règles de sécurité.
- **Auth Service** : Gère l'authentification et l'autorisation des utilisateurs, en utilisant des tokens JWT pour sécuriser les sessions.
- **Product Service** : Gère les produits et les informations associées, avec des fonctionnalités de recherche et de filtrage.
- **Order Service** : Gère les commandes des utilisateurs, intégrant des mécanismes de validation et de traitement des paiements.
- **Notification Service** : Envoie des notifications par e-mail et SMS, utilisant des services tiers comme Twilio et AWS SES.

## Architecture de l'Application
L'architecture est basée sur des microservices, permettant une gestion modulaire et indépendante des différents composants. Chaque service est conteneurisé avec Docker et déployé sur Kubernetes, assurant une scalabilité et une résilience optimales.

## Procédure de Conteneurisation
Chaque service a son propre `Dockerfile` qui définit l'environnement d'exécution. Un fichier `docker-compose.yml` est utilisé pour orchestrer les conteneurs lors du développement local, facilitant ainsi le démarrage et l'arrêt des services.

## Configuration et Déploiement de l'Infrastructure sur le Cloud
L'application est déployée sur un fournisseur de cloud (AWS ou Azure) en utilisant Kubernetes pour la gestion des conteneurs. Les configurations de déploiement sont définies dans des fichiers YAML, permettant une gestion simplifiée des ressources.

## Création et Mise en Œuvre du Pipeline CI/CD
Un pipeline CI/CD est mis en place à l'aide de GitHub Actions. Ce pipeline inclut :
- L'analyse de code et les tests automatisés pour garantir la qualité du code.
- La construction et le déploiement des images Docker, assurant que les dernières modifications sont rapidement mises en production.
- Des notifications Slack pour informer l'équipe des résultats des builds et des déploiements.

## Outils de Collaboration Utilisés
Des outils comme GitHub pour la gestion de code source et Slack pour la communication entre les membres de l'équipe ont été utilisés pour faciliter la collaboration. Trello a également été utilisé pour la gestion des tâches et le suivi des progrès.

## Mise en Place de la Pratique des Small Batches
La pratique des Small Batches a été adoptée pour favoriser des déploiements fréquents et rapides, permettant ainsi de mesurer la fréquence des déploiements et d'optimiser l'efficacité du processus. Cela réduit également le risque d'erreurs en limitant la taille des modifications apportées à chaque déploiement.

## Mesures de Performance
Des outils de surveillance comme Prometheus et Grafana sont intégrés pour suivre les performances de l'application et détecter les anomalies. Des tests de charge sont également prévus pour évaluer la capacité de l'application à gérer des volumes élevés de trafic.

## Conclusion
Ce projet a permis de mettre en pratique les principes DevOps, en favorisant la collaboration, l'automatisation et la résilience de l'application. Les étapes décrites dans ce rapport fournissent une base solide pour des développements futurs et des améliorations continues.
