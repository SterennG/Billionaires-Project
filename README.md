# Analyse & Prédiction | Origine des fortunes mondiales

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg) ![Scikit-Learn](https://img.shields.io/badge/Library-Scikit__Learn-orange.svg) ![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)

## Contexte du projet

Dans un contexte économique mondial en mutation, comprendre la dynamique de création de richesse est crucial. 
Ce projet analyse une base de données de **2 640 milliardaires (2023)** pour répondre à une question centrale :
**Quels sont les facteurs déterminants qui séparent les entrepreneurs ("Self-Made") des héritiers ?**


## Structure du répertoire

Le projet est organisé en deux notebooks séquentiels :

### 1. `billionaires_EDA.ipynb` (Exploration & Nettoyage)

*  **Objectif** : préparer le terrain et comprendre les grandes tendances.

*  **Contenu** : nettoyage des données, imputation complexe des données macro-économiques, et visualisation descriptive (impact de la fiscalité, éducation, répartition géographique...).

*  **Output** : génération du dataset propre billionaires_cleaned.csv.

### 2. `billionaires_ML.ipynb` (Modélisation & IA)

- **Objectif** : déployer les algorithmes d'apprentissage automatique.

- **Volet supervisé (prédiction)** : entraînement de modèles (Régression logistique, Random Forest, XGBoost...) pour prédire l'origine de la fortune (Recall atteint sur la classe minoritaire des héritiers : 70%).

- **Volet non-supervisé (segmentation)** : utilisation du Clustering (K-Means) pour identifier 9 profils types et comprendre la structure sociologique fine que les graphiques simples ne montraient pas.

## Résultats Clés

### 1. Modélisation prédictive (XGBoost)
Face à un jeu de données déséquilibré (majorité de Self-Made), notre défi était d'identifier correctement la classe minoritaire (Héritage).
* **Performance :** Le modèle final atteint un **Recall (Rappel) de 70%** sur les héritiers (contre 37% pour la baseline).
* **Facteurs Déterminants :** L'origine géographique (Chine vs USA), le Genre et le Secteur d'activité sont les prédicteurs les plus puissants. La fiscalité du pays n'a aucun impact significatif.

### 2. Segmentation (K-Means)
L'analyse non-supervisée a révélé **9 archétypes de milliardaires**, prouvant que la richesse mondiale n'est pas homogène :
* *L'usine du monde :* industriels chinois (97% Self-Made).
* *L'exception américaine :* une stratification unique entre "Classe moyenne des milliardaires" (Finance) et "Titans" (Tech/Retail).
* *Les dynasties :* profils européens et indiens où l'héritage prédomine.

## Stack Technique

* **Langage :** Python
* **Data Manipulation :** Pandas, NumPy
* **Visualisation :** Plotly Express (interactif), Matplotlib, Seaborn
* **Machine Learning :**
    * *Preprocessing :* Scikit-learn (`ColumnTransformer`, `Pipeline`, `Imputer`)
    * *Modèles :* Logistic Regression, Decision Tree, Random Forest, AdaBoost, **XGBoost** (retenu)
    * *Clustering :* K-Means, PCA (réduction de dimension)

## Installation & Utilisation

1.  Cloner le projet :
    ```bash
    git clone [https://github.com/sterenng/billionaires-analysis.git](https://github.com/sterenng/billionaires-project.git)
    ```
2.  Installer les dépendances :
    ```bash
    pip install pandas numpy scikit-learn xgboost plotly seaborn matplotlib
    ```
3.  Lancer le notebook d'exploration pour générer le fichier nettoyé, puis le notebook ML.

## Pistes d'Amélioration

* **Feature Engineering NLP :** scraper et analyser les biographies textuelles pour détecter des mots-clés ("founded", "inherited") afin de mieux séparer les profils mixtes occidentaux.
* **SMOTE :** utiliser la génération de données synthétiques pour équilibrer davantage les classes lors de l'entraînement.


---
Auteure : Stérenn GÉLÉOC 

Projet réalisé dans le cadre de la certification CDSD (Concepteur Développeur en Science des Données) \

Bloc 6 - Direction de projets de gestion de données
> *Objectif : traduire une problématique métier en solution Data Science, de l'exploration à la modélisation.*

JEDHA | Fullstack Data Science - Lead a Data Project - Final Project | 2025