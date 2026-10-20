# Classification du risque des assurés

## Présentation du projet

Ce projet de Machine Learning, réalisé en groupe dans le cadre de la formation à l'Université de Versailles Saint-Quentin, porte sur la prédiction du niveau de risque des assurés à partir de caractéristiques démographiques, socio-économiques, comportementales et médicales.

L'objectif est de construire et d'évaluer des modèles de classification capables de distinguer les assurés selon leur niveau de risque (`is_high_risk`).

## Objectifs

- Explorer et analyser les données afin d'identifier les principales caractéristiques des assurés.
- Préparer les données pour leur utilisation dans des modèles de Machine Learning.
- Étudier la structure des données à l'aide de méthodes de réduction de dimension.
- Comparer plusieurs algorithmes de classification supervisée.
- Évaluer les performances des modèles et analyser leurs erreurs de prédiction.

## Données

Le projet utilise le fichier `medical_insurance.csv`, contenant notamment les catégories de variables suivantes :

- **Démographiques et socio-économiques :** âge, sexe, région, situation professionnelle et taille du ménage.
- **Habitudes de vie :** indice de masse corporelle (BMI), tabagisme et fréquence de consommation d'alcool.
- **Santé :** pression artérielle, indicateurs biologiques et antécédents médicaux.
- **Utilisation des soins :** consultations, hospitalisations et médicaments.

La variable cible est `is_high_risk`, qui représente la classe de risque à prédire. La variable `risk_score` est exclue des variables explicatives dans la préparation initiale.

## Méthodologie

### 1. Analyse exploratoire

- Étude des distributions des variables numériques et catégorielles.
- Analyse des relations entre les variables explicatives et la variable cible.
- Étude des corrélations entre variables numériques.

### 2. Prétraitement des données

- Gestion des valeurs manquantes.
- Encodage ordinal des variables catégorielles ordonnées.
- Encodage One-Hot des variables catégorielles nominales.
- Standardisation des variables avant l'Analyse en Composantes Principales (ACP).

### 3. Réduction de dimension

Deux méthodes sont explorées :

- **ACP (Analyse en Composantes Principales)** : réduction de dimension en conservant des axes représentant une partie de la variabilité des données.
- **t-SNE** : représentation en deux dimensions pour explorer la structure des données et le chevauchement éventuel entre les classes.

### 4. Modélisation

Trois algorithmes de classification sont étudiés :

- Régression logistique.
- Support Vector Machine (SVM).
- Forêt aléatoire (*Random Forest*).

Les expérimentations utilisent des représentations réduites des données, notamment issues de l'ACP et de t-SNE.

### 5. Évaluation

Les modèles sont évalués sur un ensemble de test représentant 30 % des données, à l'aide de :

- Matrices de confusion.
- Rapports de classification.
- Précision (*precision*), rappel (*recall*) et F1-score.

L'analyse de ces métriques permet d'étudier les performances globales et les erreurs propres à chaque classe.

## Technologies utilisées

- Python
- Pandas et NumPy
- Matplotlib et Seaborn
- Scikit-learn
- Jupyter Notebook

## Pistes d'amélioration

- Comparer les modèles sur un protocole d'évaluation commun et reproductible.
- Optimiser les hyperparamètres et comparer les résultats obtenus.
- Étudier l'influence du déséquilibre éventuel entre les classes.
- Examiner les variables les plus importantes pour la prédiction.
- Évaluer la robustesse des modèles sur des données non utilisées pendant l'entraînement.

## Auteurs

Projet réalisé en groupe par Fatimata Tall, Samafou Koumla et Frejuste Abinonkpa.

Université de Versailles Saint-Quentin — 8 janvier 2026.
