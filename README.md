# IPU_segmentation Segmentation d'audios en IPU (Inter-Pausal Units)

## Description
Ce dépôt contient deux notebooks permettant de segmenter des fichiers audio en unités inter-pausales (IPU) :

1. **Segmentation avec SPASS** : Ce notebook utilise le logiciel SPASS pour effectuer la segmentation.
2. **Segmentation avec une méthode personnalisée** : Ce notebook propose une méthode personnalisée basée sur un percentile pour définir le seuil de silence et réaliser la segmentation.

Les IPU sont des segments d’audio délimités par des pauses silencieuses.

## Contenu
- **`segmentation_SPASS.ipynb`** : Ce notebook décrit comment utiliser SPASS pour segmenter les fichiers audio. Il inclut des étapes pour :
  - Charger les fichiers audio
  - Configurer les paramètres de segmentation de SPASS
  - Obtenir et analyser les résultats de segmentation

- **`segmentation.ipynb`** : Ce notebook présente une approche maison pour la segmentation, basée sur :
  - L’analyse des amplitudes audio
  - L’utilisation d’un seuil défini à partir d’un percentile pour détecter les pauses
  - La création des segments d'IPU
