# 🏡 House Price Prediction Project

Ce projet a pour objectif de prédire le prix de maisons à partir de leurs caractéristiques (surface, nombre de chambres, emplacement, etc.) à l'aide de plusieurs modèles de régression.

---

## 📁 Dataset

Le dataset utilisé est un fichier CSV (`data.csv`) contenant **4 600** entrées et **18 colonnes**, incluant :

- `price` (la variable cible)
- `bedrooms`, `bathrooms`, `sqft_living`, `floors`, `waterfront`, etc.
- `street`, `city`, `statezip`, `country`

---

## 🔍 Étapes du projet

### 1. Chargement et exploration des données

- Vérification des colonnes, types de données, valeurs manquantes (aucune).
- Analyse statistique (`describe()`)
- Visualisations (histogrammes, heatmap de corrélation, boxplots)

### 2. Détection et suppression des outliers

Utilisation de l'IQR pour détecter et filtrer les valeurs aberrantes.  
**Résultat :** de 4 600 à **3 316 lignes**.

### 3. Encodage des variables catégorielles

Encodage `OneHot` des colonnes `city`, `statezip`, et `country` via `pd.get_dummies`.

### 4. Feature Engineering

Ajout de nouvelles colonnes : `year`, `month`, `day` à partir de la colonne `date`.

### 5. Split des données

- 80% entraînement, 20% test
- Suppression de la colonne non numérique `street`

---

## 🤖 Modèles de Machine Learning

4 modèles supervisés testés :

- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor ✅
- XGBoost Regressor

---

## 📊 Résultats des modèles

| Modèle             | RMSE        | R² Score |
|--------------------|-------------|----------|
| Decision Tree      | 207,836.16  | -0.13    |
| Random Forest      | 148,211.33  | 0.42     |
| Gradient Boosting  | **141,561.28** | **0.47** |
| XGBoost            | 156,989.90  | 0.35     |

🔹 **Gradient Boosting** donne les meilleurs résultats.  
🔹 Random Forest est également performant.  
🔹 XGBoost nécessite un tuning plus poussé.

---

## 📈 Visualisations

Visualisations des prédictions comparées aux valeurs réelles (`y_test`) pour chaque modèle via `scatterplot`.

- Les points proches de la diagonale indiquent une bonne précision.
- Gradient Boosting est celui qui colle le plus à la réalité.

---

## 🚀 Exécution du projet

### 📦 Prérequis

```bash
pip install numpy pandas seaborn matplotlib scikit-learn xgboost

