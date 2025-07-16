# 🏡 House Price Prediction Project

This project aims to predict house prices based on various property features using multiple regression models.

---

## 📁 Dataset

The dataset used is a CSV file (`data.csv`) containing **4,600** entries and **18 columns**, including:

- `price` (target variable)
- `bedrooms`, `bathrooms`, `sqft_living`, `floors`, `waterfront`, etc.
- `street`, `city`, `statezip`, `country`

---

## 🔍 Project Workflow

### 1. Data Loading & Exploration

- Checked column types and missing values (none found).
- Generated descriptive statistics (`describe()`)
- Plotted data distributions, heatmap for correlation, and boxplots for outlier detection.

### 2. Outlier Detection & Removal

Used IQR method to remove outliers.  
**Result:** Reduced dataset from 4,600 to **3,316 rows**.

### 3. One-Hot Encoding

Applied one-hot encoding to `city`, `statezip`, and `country` using `pd.get_dummies`.

### 4. Feature Engineering

Extracted new date-related features: `year`, `month`, and `day` from the `date` column.

### 5. Train-Test Split

- 80% training, 20% test
- Removed the non-numeric `street` column

---

## 🤖 Machine Learning Models

Four regression models were trained and evaluated:

- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor ✅
- XGBoost Regressor

---

## 📊 Model Performance

| Model              | RMSE         | R² Score |
|--------------------|--------------|----------|
| Decision Tree      | 207,836.16   | -0.13    |
| Random Forest      | 148,211.33   | 0.42     |
| Gradient Boosting  | **141,561.28** | **0.47** |
| XGBoost            | 156,989.90   | 0.35     |

🔹 **Gradient Boosting** delivered the best performance.  
🔹 Random Forest also performed well.  
🔹 XGBoost could benefit from hyperparameter tuning.  
🔹 Decision Tree showed signs of overfitting.

---

## 📈 Visualizations

Scatter plots were created to compare actual vs. predicted prices.

- **Gradient Boosting** predictions were closest to the diagonal line (ideal case).
- **Random Forest** also showed strong clustering.
- **Decision Tree** had significant spread — indicating poor generalization.

---

## 🚀 How to Run the Project

### 📦 Requirements

```bash
pip install numpy pandas seaborn matplotlib scikit-learn xgboost
