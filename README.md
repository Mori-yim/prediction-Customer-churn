Telco Customer Churn Prediction – MLOps Project
 Description du Projet
Dans le secteur des télécommunications, la rétention client est un enjeu stratégique majeur. Ce projet vise à construire un système de prédiction robuste capable d'identifier les clients susceptibles de quitter l'opérateur (Churn).

L'approche adoptée suit les standards MLOps : de l'analyse exploratoire rigoureuse à la création d'un pipeline de production sérialisé.

 Dataset
Le projet utilise le dataset Telco Customer Churn (Kaggle).

Taille : 7043 clients.

Variables : Démographie, services souscrits, informations contractuelles et financières.

Cible : Churn (Yes/No).

 Pipeline Technique (Architecture)
1. Analyse Exploratoire (EDA)
Investigation approfondie des données pour identifier les leviers du churn :

Qualité des données : Traitement des valeurs manquantes dans TotalCharges.

Corrélations : Identification de l'impact majeur du type de contrat et de l'ancienneté (tenure).

Tests Statistiques : Validation de la significativité des features.

2. Feature Engineering & Preprocessing
Mise en place d'un ColumnTransformer automatisé :

Numérique : Standardisation via StandardScaler.

Catégoriel : Encodage via OneHotEncoder avec gestion des valeurs inconnues.

Pipeline : Garantit l'absence de Data Leakage entre les ensembles de train et de test.

3. Modélisation & Benchmarking
Évaluation de 6 algorithmes pour sélectionner le "Champion" :

Logistic Regression (Baseline)

Random Forest

XGBoost (Vainqueur)

SVM

KNN

AdaBoost

4. Optimisation & Interprétabilité
Hyper-tuning : Recherche par grille (GridSearchCV) pour optimiser le score ROC-AUC.

XAI (Explainable AI) : Analyse de l'importance des variables pour fournir des recommandations métier actionnables.

📈 Résultats Clés
Modèle retenu : XGBoost

ROC-AUC Score : ~0.84

Recall : Optimisé pour capturer un maximum de départs potentiels.

Top Facteurs de Churn : Contrats "Month-to-month", Fibre Optique, Faible ancienneté.

 Installation & Utilisation
Prérequis
Bash
pip install pandas numpy scikit-learn xgboost seaborn matplotlib joblib
Exécution du projet
Entraînement : Lancez le script principal pour générer le modèle.

Production : Le modèle est sauvegardé sous telco_churn_pipeline.pkl.

Inférence : Utilisez joblib.load() pour prédire sur de nouvelles données.

📂 Structure du Dépôt
Plaintext
├── data/
│   └── Customer_Churn.csv  # Données brutes
├── notebooks/
│   └── EDA_and_Modeling.ipynb                # Analyse et tests
├── src/
│   ├── clean_data.py                         # Scripts de nettoyage
│   └── train_pipeline.py                     # Pipeline d'entraînement
├── models/
│   └── telco_churn_pipeline.pkl              # Modèle sérialisé
└── README.md
 Recommandations Métier
Action 1 : Inciter les clients en contrat mensuel à passer sur des engagements annuels via des promotions ciblées.

Action 2 : Améliorer l'onboarding des nouveaux clients durant les 6 premiers mois.

Action 3 : Auditer la satisfaction des clients équipés de la Fibre Optique.

Auteur : [Morino Ymfack]

Poste : MLOps Engineer / Data Scientist et developpeur wer junior
