---
title: Assistant de documentation pour campagnes de pentest, GRC et audit ISO 27001
description: Stage de fin d'année
date: 2025-07-01
image: yuften.jpeg
tags: 
  - Pentest
  - GRC
  - AuditSSI
  - ISO27001
  - Conformité
  - Java
  - PowerBI
  - LLM
  - Cybersécurité
  - DocumentationAutomatisée
categories:
    - Expérience professionelle
---
## Contexte du projet

Dans le cadre de mon stage de Master 1 en cybersécurité chez **Yuften Services**, je développe un **assistant logiciel de génération de rapports d’audit et de pentest**, destiné à automatiser la documentation technique tout en intégrant une évaluation de conformité selon **ISO/IEC 27001**. Ce projet s’inscrit dans une logique GRC (Gouvernance, Risques et Conformité), en soutenant les processus d’audit, de traçabilité et de suivi des mesures de sécurité.

## Objectifs

- Concevoir un assistant automatisé capable de générer des rapports complets et structurés à chaque étape d’une campagne de test d’intrusion.
- Intégrer une **cartographie des exigences ISO/IEC 27001** en lien avec les constats techniques observés lors des audits.
- Fournir une **visualisation des écarts et niveaux de conformité** via un tableau de bord Power BI.
- Renforcer les capacités internes de Yuften Services en matière de GRC, en particulier dans la formalisation des livrables d’audit.

## Architecture du projet

L’assistant repose sur les composants suivants :

- **Un moteur Java connecté à un LLM** (via OpenRouter API), chargé de générer automatiquement le contenu des rapports de pentest.
- Un **module d’évaluation ISO 27001**, basé sur un tableau de correspondance entre les vulnérabilités et les contrôles de la norme (Annexe A).
- Un **formulaire interactif**, utilisé par les auditeurs pour alimenter les résultats techniques.
- Un tableau de bord **Power BI**, centralisant :
  - La couverture des contrôles ISO
  - Le suivi des vulnérabilités identifiées
  - L’état d’avancement des recommandations
  - L’exposition aux risques organisationnels

## Technologies utilisées

- **Java** (Spring Boot) : logique d’assistant, traitement des données.
- **OpenRouter API / LLM** : génération intelligente de contenu technique.
- **ISO/IEC 27001** : structure de conformité et axes d’analyse.
- **Power BI** : visualisation des indicateurs de conformité et de risque.
- **Excel/JSON** : support structuré des données (vulnérabilités, contrôles, plans d’action).

## Avancement actuel

- Le moteur Java est fonctionnel pour générer automatiquement les sections de rapport (introduction, méthodes, vulnérabilités, recommandations).
- La cartographie avec les exigences ISO est en cours d’intégration, avec plusieurs contrôles déjà couverts (A.5, A.6, A.8...).
- Le tableau de bord Power BI est opérationnel pour afficher les niveaux de conformité et l’état des actions.

## Résultat attendu

Ce projet permet à Yuften Services de :
- **Améliorer la productivité et la qualité des audits techniques**.
- **Standardiser les livrables**, en s’alignant sur les exigences normatives.
- **Valoriser une approche GRC** auprès des clients professionnels.
- **Appuyer les décisions de sécurité** grâce à une visualisation claire des écarts et des priorités.

C’est un projet à fort impact qui me permet de croiser les domaines de la **cybersécurité offensive, de la gouvernance et de l’audit**, tout en appliquant mes compétences techniques dans un contexte réel.
