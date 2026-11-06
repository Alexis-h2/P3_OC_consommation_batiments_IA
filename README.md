# Projet 3 Anticipez les besoins en consommations de bâtiments
Modèle IA de prédiction de consommation des bâtiments

1. Contexte et Objectifs du ProjetLa ville de Seattle s'est fixé pour objectif d'atteindre la neutralité carbone d'ici 2050. Pour y parvenir, la municipalité a recueilli des données structurelles et énergétiques détaillées sur les bâtiments non résidentiels. L'objectif de ce projet est de concevoir un système prédictif basé sur des algorithmes d'apprentissage automatique supervisé pour estimer : La consommation totale d'énergie (SiteEnergyUse(kBtu)).Les émissions de gaz à effet de serre (TotalGHGEmissions en tonnes métriques .

2. Démarche Méthodologique & Prévention des Fuites de DonnéesLe projet met en œuvre les standards de modélisation prédictive tabulaire :Découpage des données : Séparation stricte initiale entre un jeu d'entraînement (80 %) et un jeu de test final (20 %, isolé et jamais vu avant l'audit final).Herméticité du préprocessing (Anti-Data Leakage) : Utilisation systématique de la classe Pipeline de Scikit-Learn combinée à ColumnTransformer. L'ajustement des transformations (calcul des moyennes/écarts-types par StandardScaler, tables de correspondance du OneHotEncoder) est recalculé à l'intérieur de chaque pli lors de la validation croisée (KFold(n_splits=5)).Stabilisation de la variance de la cible : Modélisation sur cibles transformées par logarithme népérien (ln(1+y)) afin de normaliser les distributions fortement asymétriques. 

3. Structure du Répertoire├── data/
raw : 2016_Building_Energy_Benchmarking.csv   # Données brutes de la ville de Seattle (2016)
notebook : Hernandez_Alexis_1_notebook_102026.ipynb
requirements.txt           # Dépendances Python du projet
README.md                  # Documentation du projet

4. Modèle ML selectionné : Light GBM
Résultats en fin de note book 
Conclusions métier rédigées dans un PPT en dehors du repo

