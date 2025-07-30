---
title: "Système de contrôle de sécurité pour la conduite autonome sur autoroute"
description: 
date: 2025-05-7
image: schema.png
Categories: 
     - Projects

---
## Contexte du projet

Ce projet a été réalisé dans le cadre du module de Spécification et Vérification Formelle. Il s’agit d’un **cas d’étude proposé lors de la conférence internationale ABZ 2025**, visant à modéliser un **contrôleur de sécurité embarqué** pour la conduite autonome sur autoroute, en environnement multi-voies.

Le système développé intervient comme une **surcouche de supervision** indépendante, capable de valider, corriger ou bloquer les décisions prises par une intelligence artificielle de pilotage. L’objectif est d’éviter toute situation de collision ou de non-respect des règles de conduite, tout en assurant un comportement globalement sûr du véhicule.

## Objectifs

- Modéliser un système capable d’assurer une **conduite autonome sans collision** dans un environnement autoroutier dynamique.
- Intégrer un **mécanisme de contrôle vérifiable** qui réagit aux événements du trafic (accélération, freinage, changement de voie).
- Garantir la **sécurité formelle** du système à chaque cycle de perception-décision-action.
- Utiliser des outils dédiés pour **prouver l’absence d’erreurs** par model checking.

## Méthodologie

Le modèle a été spécifié en langage **Event-B**, un formalisme mathématique orienté sécurité, puis vérifié automatiquement à l’aide de l’outil **ProB**.

Le système simule deux véhicules évoluant sur deux voies, avec des actions limitées :
- Accélérer
- Freiner
- Maintenir la vitesse
- Changer de voie à gauche ou à droite

Les contraintes de sécurité incluent :
- Le respect d’une **distance minimale** de sécurité entre véhicules
- L’interdiction du chevauchement latéral lors des changements de voie
- Un modèle de réaction en cas d’urgence (freinage immédiat, blocage des actions dangereuses)

## Aspects techniques clés

- Utilisation d’**invariants de sécurité** pour garantir la non-collision
- Mise en œuvre d’une **formule simplifiée inspirée du modèle RSS** pour calculer dynamiquement les distances de sécurité
- Modèle structuré par **cycles de décision de 1 seconde**, simulant un comportement temps réel
- Validation de plus de **3,2 millions d’états simulés sans erreur détectée** grâce à ProB
- Contrôleur organisé autour d’un **ensemble d’événements discrets sécurisés**, incluant un système de détection de collision, de changement de voie contrôlé, et de cycle d’observation planifié

## Technologies et outils utilisés

- Event-B (modélisation formelle)
- ProB (vérification automatique, animation, model checking)
- Rodin Platform (IDE Event-B)
- Méthodologie de conception orientée sûreté (modèle déterministe, invariants, règles conditionnelles)

## Résultat

Le système spécifié garantit un **comportement sans collision** dans tous les scénarios testés. L’analyse exhaustive avec ProB confirme que **toutes les propriétés de sûreté sont respectées**, et que **les événements critiques sont toujours contrôlés par des garde-fous formels**. L’absence de déclenchement de l’événement `Detecter_collision` prouve que le système empêche les situations dangereuses avant même qu’elles ne puissent survenir.

## Conclusion

Ce projet montre comment une **approche formelle rigoureuse** peut permettre de modéliser et vérifier des systèmes critiques à haute exigence de sécurité. Il illustre la possibilité de concevoir des modules de supervision robustes pour la conduite autonome, capables d’intervenir de manière déterministe et vérifiable sur les décisions prises par une IA embarquée.

Le modèle constitue une base fiable pour étendre cette logique à des scénarios plus complexes : davantage de véhicules, événements aléatoires, ou pannes simulées.

## Visualisation

![Architecture logique](scheam.png)  
![Simulation ProB](projet_svf_6.png)