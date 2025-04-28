---
title: Système Domotique Intelligent
date: 2025-01-07
image: iotrap2CIRCUIT.png
tags: 
    - IOT
    - Domotique
    - MQTT
    - HTTP
    - HiveMQ
    - Wokwi
    - NodeRED
    - THingspeak
categories:
    - Projects
    - IOT
---
## Objectif
L’objectif de ce projet est de concevoir et de simuler un système domotique intelligent permettant la surveillance et le contrôle à distance de différents paramètres environnementaux. Ce système utilise un microcontrôleur ESP32 pour la collecte de données à partir de capteurs (température, humidité, lumière, mouvement) et leur transmission à des plateformes cloud via les protocoles MQTT et HTTP.MQTT est utilisé pour l’envoi des données vers une interface sur Node-RED qui permet d’afficher les valeurs en temps réel et de contrôler certains composants à distance, tandis que HTTP est utilisé pour l’envoi des données vers ThingSpeak.

## Wokwi
Wokwi a été utilisé pour la simulation du système, permettant l’intégration des composants suivants :
— Capteur DHT22 : Surveillance de la température et de l’humidité avec activation d’un ventilateur (LED bleue) si la température dépasse 30°C, activation d’un buzzer au-delà de 45°C, et activation d’un déshumidificateur (LED verte) si l’humidité excède 70
— Capteur PIR : Détection de mouvement avec affichage sur un LCD I2C.
— Capteur LDR : Mesure de l’intensité lumineuse et allumage automatique d’une LED si la luminosité est inférieure à 500 lux.
— Servo moteur : Simulation d’une pompe à eau, contrôlable via un "slider" depuis Node-RED.
— LED Neopixel : Simulation d’un système d’éclairage RGB, contrôlable via un "color picker" depuis Node-RED.

## NodeRED
Envoi des données via MQTT : J’ai utilisé le serveur public HiveMQ pour la transmission des valeurs des capteurs vers Node-RED pour un traitement et un affichage en temps réel.
— Affichage en temps réel : Données de température, d’humidité et de luminosité (sous forme de jauges et graphiques), et détection de mouvement (notification d’alerte popup).
— Contrôle des composants :
— Activation/désactivation de la LED (même LED utilisé quand la luminosité est inférieure à 500 lux) via un switch.
— Contrôle du servo-moteur à l’aide d’un slider.
— Modification de la couleur de la LED Neopixel via un "color picker".
— Stockage des données : Utilisation d’un noeud "write file" pour enregistrer les valeurs captées avec un timestamp dans un fichier dataiot.txt.

## Thingspeak
Un channel "Système Domotique Intelligent" a été créé sur ThingSpeak pour recevoir les données via le protocole HTTP et les afficher sous forme de graphiques. 
Quatre fields ont été créés dans le channel, permettant le stockage des données respectivement pour la température, l’humidité, la détection de mouvement et l’éclairage.
Les valeurs envoyées sont mises à jour en temps réel pour un suivi précis des paramètres environnementaux.

## Project Demo Video

<video controls width="700">
  <source src="/markdown-syntax/video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
