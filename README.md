# 🚗 Car Price Prediction Using Machine Learning

## 📊 Project Overview

This project builds a production-ready price prediction system for used cars in the Indian market using state-of-the-art machine learning algorithms. The model analyzes various car features (brand, age, mileage, fuel type, etc.) to provide accurate price estimates.

### Key Achievements
- **65.59% R² Score** - Explains 65.6% of price variance
- **₹390,844 Average Error** - Competitive prediction accuracy
- **4 ML Algorithms** - Comprehensive model comparison
- **SHAP Explainability** - Transparent, interpretable predictions
- **Production-Ready** - Deployed and scalable

---

## 🎯 Results Summary

### Model Performance (Clean Dataset: 3,577 unique cars)

| Model | R² Score | RMSE | MAE | Overfit Gap |
|-------|----------|------|-----|-------------|
| **XGBoost** ⭐ | **65.59%** | **₹390,844** | **₹241,097** | 0.319 |
| CatBoost | 60.95% | ₹416,384 | ₹237,783 | 0.316 |
| RandomForest | 58.84% | ₹427,443 | ₹244,759 | 0.346 |
| LightGBM | 58.27% | ₹430,414 | ₹264,599 | 0.275 |

**Best Model:** XGBoost achieved the highest R² score with the lowest RMSE.

--

## 🛠️ Tech Stack

### Core Libraries
- **Python 3.8+**
- **Pandas & NumPy** - Data manipulation
- **Scikit-learn** - ML pipeline and preprocessing
- **Matplotlib & Seaborn** - Data visualization

### Machine Learning
- **LightGBM** - Microsoft's gradient boosting framework
- **XGBoost** - Extreme gradient boosting (best performer)
- **CatBoost** - Yandex's gradient boosting with categorical support
- **RandomForest** - Ensemble of decision trees

### Advanced Features
- **Optuna** - Bayesian hyperparameter optimization
- **SHAP** - Model interpretability and feature importance
- **Stacking Ensemble** - Combining multiple models

---

## 🚀 Quick Start

### Google Colab (Recommended)
1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload `car_data.csv`
3. Run all cells (Runtime → Run all)

### Local Setup
```bash
# Clone the repository
git clone https://github.com/yourusername/car-price-prediction.git
cd car-price-prediction

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook car_price_prediction.ipynb
```

---

## 📖 Methodology

### 1. Data Cleaning
- **Original dataset:** 4,340 rows
- **Removed duplicates:** 763 rows (17.6%)
- **Final dataset:** 3,577 unique cars

### 2. Feature Engineering

Created 12 advanced features:
- `car_age` - Current year - manufacturing year
- `brand` - Extracted from car name
- `is_luxury` - Binary indicator for luxury brands
- `age_km_interaction` - Wear and tear proxy
- `km_per_year` - Usage intensity
- `brand_avg_price` - Target encoding for brand
- And 6 more...

### 3. Model Training

**Train-Test Split:**
- Time-based split (85% train, 15% test)
- Train: 2000-2022 cars | Test: 2023-2024 cars

**Models Compared:**
- LightGBM
- XGBoost (winner)
- CatBoost
- RandomForest

---

## 🔍 Model Interpretability

### SHAP Analysis

**Top 5 Most Important Features:**
1. **Car Age** (35%) - Strongest predictor
2. **Brand** (25%) - Luxury brands command premium
3. **KM Driven** (20%) - Higher mileage = lower price
4. **Fuel Type** (10%)
5. **Transmission** (5%)

---

## 📈 Error Analysis

### Prediction Accuracy
- **Within ±20%:** ~70% of predictions
- **Within ±30%:** ~85% of predictions

### Where Model Struggles
- Rare car models (limited examples)
- Extreme prices (<₹1L or >₹20L)
- Missing features (condition, accident history)
