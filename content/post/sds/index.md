---
title: "Système Distribué Intelligent pour l’Agriculture de la Betterave"
description: 
date: 2025-02-28T20:14:08Z
image: sds.png
Categories: 
     - Projects
math: 
license: 
hidden: false
comments: true
draft: true
---
## Contexte du projet

Ce projet a été réalisé dans le cadre du module "Systèmes Distribués et Services", avec pour objectif de concevoir une solution technologique permettant la surveillance en temps réel des paramètres environnementaux d’une culture de betteraves. Il s’inscrit dans une approche d’agriculture connectée, visant à améliorer la gestion des cultures par la collecte, le traitement et la visualisation intelligente des données issues du terrain.

## Objectifs

Le système développé permet de suivre des indicateurs clés comme la température, l’humidité et le pH du sol, afin d’optimiser les pratiques agricoles (arrosage, apport d’intrants, prévention des anomalies). L’architecture repose sur une combinaison de **microservices Java**, d’un **middleware de streaming Kafka**, d’un **stockage cloud Firebase** et d’une **interface de visualisation via Node-RED**.

## Architecture technique

L’infrastructure du système est organisée comme suit :

- **Trois microservices spécialisés** dans la collecte de données simulées :
  - Température (via Sockets TCP)
  - pH du sol (via JAX-WS)
  - Humidité (via Spring Boot)

- **Kafka** assure la transmission asynchrone et fluide des données entre producteurs (microservices) et consommateurs (Firebase + Tableau de bord).

- **Firebase Realtime Database** stocke les données de manière structurée, facilitant leur exploitation et leur mise à jour instantanée.

- **Node-RED** récupère les données depuis Firebase pour créer un **tableau de bord interactif**, accessible en local via navigateur.

## Fonctionnalités développées

- **Génération automatique de données simulées** pour température, pH et humidité, avec fréquence ajustée par programmation.
- **Stockage structuré dans Firebase**, avec timestamp.
- **Traitement des flux** dans Node-RED :
  - Extraction des données depuis Firebase
  - Détection des dépassements de seuils
  - Génération d’alertes en cas de conditions défavorables
- **Affichage des indicateurs** sous forme de jauges, graphiques dynamiques et notifications contextuelles dans un tableau de bord appelé *Betterave’s Dashboard*.

## Technologies utilisées

- Java / Spring Boot
- Sockets TCP / JAX-WS (Web Services SOAP)
- Apache Kafka
- Firebase Realtime Database
- Node-RED
- Eclipse (IDE)
- Maven

## Résultat

Le système fonctionne de manière distribuée et asynchrone, permettant une supervision continue de la culture. Les agriculteurs peuvent ainsi :
- Consulter les mesures environnementales à distance
- Recevoir des alertes en cas de dépassement de seuils critiques (ex. température hors plage optimale)
- Appuyer leurs décisions sur des données fiables, accessibles en temps réel

Ce projet ouvre des perspectives vers une agriculture plus connectée et pilotée par les données, avec la possibilité d’intégrer des modules supplémentaires (recommandations automatiques, autres capteurs, machine learning).

