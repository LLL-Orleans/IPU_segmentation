# Segmentation_auto : Segmentation d'audios en IPU (Inter-Pausal Units)

## Description

Ce dépôt contient des notebooks relatifs à la segmentation automatique des fichiers audio en unités inter-pausales (IPU). Les IPU sont des segments audio délimités par des pauses silencieuses, souvent utilisés en linguistique et en analyse de la parole pour étudier la structure des discours.

### Fonctionnalités principales :
1. **Conversion de formats pour la visualisation croisée** :
   - **TextGrid vers EAF** : Convertit les alignements forcés au format TextGrid en fichiers EAF pour faciliter la visualisation dans des outils comme ELAN.
   - **RTTM vers EAF** : Transforme les fichiers RTTM générés par Voice Activity Detection (VAD) en fichiers EAF pour des analyses approfondies.

2. **Segmentation automatique** :
   - **Segmentation avec SPASS** : Utilise le logiciel SPASS pour effectuer une segmentation en IPU.
   - **Segmentation personnalisée** : Implémente une méthode basée sur un seuil de silence défini dynamiquement (percentile).
   - **Segmentation avec Pyannote** : Applique le modèle VAD de Pyannote pour détecter automatiquement les segments audio.

## Contenu des fichiers

### Conversion de formats
- **`textgrid2eaf.ipynb`** :
  - Convertit les fichiers TextGrid en EAF.
  - Inclut des étapes pour extraire les alignements forcés, convertir les intervalles en annotations, et générer un fichier compatible ELAN.
- **`add_rttm2eaf.ipynb`** :
  - Transforme les fichiers RTTM générés par des outils de détection d'activité vocale (VAD) en fichiers EAF pour une visualisation croisée.
  - Permet de relier les annotations de détection vocale aux segments audio correspondants.

### Segmentation
- **`segmentation_SPASS.ipynb`** :
  - Implémente l'utilisation de SPASS pour segmenter les fichiers audio.
  - Comprend :
    - Le chargement des fichiers audio.
    - La configuration des paramètres de segmentation (seuils de silence, durée minimale des segments).
    - L'analyse des résultats.
- **`segmentation_IPUs.ipynb`** :
  - Propose une méthode personnalisée de segmentation en IPU basée sur :
    - L'analyse des amplitudes audio.
    - L'application d'un seuil dynamique (calculé via un percentile).
    - La génération des segments IPU.
    - Exporte les résultats sous forme de fichiers EAF pour la visualisation croisée.
- **`pyannote_seg_copy.ipynb`** :
  - Utilise le modèle Pyannote pour la segmentation automatique via VAD.
  - Inclut des étapes pour :
    - Charger un modèle pré-entraîné Pyannote.
    - Détecter les segments vocaux dans des fichiers audio.
    - Exporte les résultats sous forme de fichiers EAF pour la visualisation croisée.

## Instructions d'utilisation
1. Clonez le dépôt :  
   ```bash
   git clone https://github.com/LLL-Orleans/Segmentation_auto.git
   cd Segmentation_auto
   ```
2. Installez les dépendances nécessaires, notamment Pyannote et les bibliothèques pour manipuler les formats TextGrid et EAF :
   ```bash
   pip install pyannote-audio pympi-ling
   ```
