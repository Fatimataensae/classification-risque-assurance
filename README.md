# Prédiction du niveau de risque des assurés

## Présentation du projet

Ce projet de Machine Learning, réalisé en groupe dans le cadre de notre formation à l'Université de Versailles Saint-Quentin (UVSQ), vise à prédire si un assuré présente un niveau de risque médical élevé à partir de caractéristiques démographiques, socio-économiques et liées à son mode de vie et à sa santé.

L'objectif est de comparer plusieurs algorithmes de classification supervisée afin d'identifier ceux qui permettent de prédire le niveau de risque des assurés.

## Objectifs

- Explorer et analyser les données afin de mieux comprendre les caractéristiques des assurés.
- Préparer les données pour leur utilisation dans des modèles de Machine Learning.
- Explorer la structure des données à l'aide de méthodes de réduction de dimension.
- Comparer plusieurs algorithmes de classification supervisée.
- Évaluer les performances des modèles à l'aide de différentes métriques.

## Données

Le jeu de données `medical_insurance.csv` provient de Kaggle.

- **Nombre d'observations :** 100 000
- **Nombre de variables :** 53
- **Variable cible :** `is_high_risk`, qui indique si un assuré appartient à la catégorie de risque élevé.

Les variables explicatives comprennent notamment l'âge, le revenu, l'indice de masse corporelle (BMI), la pression artérielle, le tabagisme et certaines habitudes de vie.

La variable `risk_score`, utilisée dans la construction de la variable cible selon la source, a été supprimée des variables explicatives.

**Source :** [Medical Insurance Cost Prediction — Kaggle](https://www.kaggle.com/datasets/mohankrishnathalla/medical-insurance-cost-prediction/data)

## Méthodologie

### 1. Analyse exploratoire des données

- Étude des variables quantitatives et qualitatives.
- Analyse de la distribution de la variable cible.
- Étude des corrélations entre les variables.
- Visualisation de la structure des données à l'aide de t-SNE.

### 2. Prétraitement des données

- Encodage des variables catégorielles nominales avec One-Hot Encoding.
- Encodage des variables catégorielles ordinales avec Ordinal Encoding.
- Imputation des valeurs manquantes, notamment pour la variable `alcohol_freq`.
- Suppression des variables jugées inutiles pour la modélisation, dont `id` et `risk_score`.

Les étapes de prétraitement ont été organisées pour éviter les fuites de données entre les ensembles d'entraînement et de test.

### 3. Réduction de dimension

- **Analyse en composantes principales (ACP)** pour étudier une représentation réduite des variables.
- **t-SNE** pour visualiser les données en deux dimensions et explorer leur structure.

### 4. Modélisation

Trois algorithmes de classification supervisée ont été étudiés :

- Régression logistique
- Support Vector Machine (SVM)
- Forêt aléatoire (*Random Forest*)

### 5. Évaluation

Les performances des modèles ont été comparées à l'aide des métriques suivantes :

- **Accuracy** : proportion de prédictions correctes.
- **ROC-AUC** : capacité à discriminer les deux classes.
- **F1-score** : moyenne harmonique de la précision et du rappel.
- **Precision** : proportion de prédictions positives qui sont effectivement positives.
- **Recall** : proportion de cas positifs correctement détectés.

## Résultats

Les résultats reportés dans la présentation du projet sont les suivants :

| Modèle | Accuracy | ROC-AUC | F1-score | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| Régression logistique | 0.8676 | 0.9468 | 0.8281 | 0.7924 | 0.8672 |
| Random Forest | **0.9935** | **0.9999** | **0.9911** | **0.9939** | **0.9884** |
| SVM | 0.8674 | 0.9468 | 0.8279 | 0.7919 | 0.8673 |

D'après ces métriques, le **Random Forest obtient les meilleures performances** sur les cinq indicateurs présentés. La régression logistique et le SVM affichent des résultats très proches.

Ces résultats doivent toutefois être interprétés en tenant compte du protocole expérimental, de la séparation entraînement/test et de la manière dont les transformations des données ont été appliquées.

## Limites et perspectives

Les principales limites identifiées au cours du projet concernent :

- Le choix et la représentativité du jeu de données.
- Le temps d'exécution de certaines méthodes.
- Le choix du nombre de composantes retenues pour l'ACP.
- L'exploration d'autres méthodes de réduction de dimension, notamment t-SNE et l'AFDM.

Parmi les perspectives d'amélioration figurent également l'optimisation des hyperparamètres, la comparaison des modèles dans un protocole expérimental commun et l'analyse de leur capacité à généraliser à de nouvelles observations.

## Technologies utilisées

- Python
- Pandas et NumPy
- Matplotlib et Seaborn
- Scikit-learn
- Jupyter Notebook

## Auteurs

Projet réalisé en groupe par **Fatimata Tall, Samafou Koumla et Frejuste Abinonkpa**, dans le cadre de notre formation à l'Université de Versailles Saint-Quentin (UVSQ).
