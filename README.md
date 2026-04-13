<p align="center"><a href="README.tr.md"><b>🇹🇷 Türkçe</b></a></p>

# 🚀 Spaceship Titanic — ML Classification Pipeline

**EDA → Feature Engineering → 3-Model Comparison → Hyperparameter Tuning → Cross-Validation**

[![Kaggle](https://img.shields.io/badge/Kaggle-Spaceship%20Titanic-blue)](https://www.kaggle.com/competitions/spaceship-titanic)
[![Python](https://img.shields.io/badge/Python-3.8+-brightgreen)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange)](https://scikit-learn.org)

> **Originally created in August 2022** — before generative AI tools became widely available. This project was developed entirely through manual data analysis, feature engineering, and model tuning as the capstone project for the **13th term of [ITU SEM Data Science Specialization Certificate Program](https://itusem.itu.edu.tr/egitimler-ve-programlar/isletme-fakultesi-sertifika-programlari/data-science--uzmanligi-sertifika-programi)**.

Kaggle's Spaceship Titanic competition — predict which passengers were transported to another dimension using data from the spaceship's luxury amenities, passenger demographics, and travel information.

## 📊 Dataset

| Feature | Description |
|---------|-------------|
| `PassengerId` | Unique ID per passenger (`gggg_pp` format: group + number) |
| `HomePlanet` | Planet of origin (Earth, Europa, Mars) |
| `CryoSleep` | Passenger elected suspended animation |
| `Cabin` | Cabin location (`deck/num/side`) |
| `Destination` | Destination planet |
| `Age` | Passenger age |
| `VIP` | Special VIP service status |
| `RoomService`, `FoodCourt`, `ShoppingMall`, `Spa`, `VRDeck` | Luxury amenity spending |
| `Name` | Passenger name |
| `Transported` | **Target** — binary classification |

## 🧪 Methodology

### 1. Exploratory Data Analysis
- Distribution analysis for continuous & categorical features
- Correlation heatmap
- Missing value detection
- Target balance check

### 2. Feature Engineering
- **PassengerId split** → group number + passenger number within group
- **Cabin split** → Deck, Cabin Number, Side (Port/Starboard)
- **Name split** → first name + surname
- **Age binning** → 3 groups (0–17, 18–42, 42+)
- **Missing value imputation** → mean for continuous, mode for categorical
- **Label encoding** for all categorical features

### 3. Modeling
Three classifiers trained with **RandomizedSearchCV** hyperparameter tuning + **5-fold cross-validation**:

| Model | Best CV Accuracy | CV Std | Overfitting |
|-------|:----------------:|:------:|:-----------:|
| **RandomForestClassifier** | **0.7974** | ±0.0070 | ✅ Low (gap: 0.017) |
| **GradientBoostingClassifier** | **0.7972** | ±0.0097 | ⚠️ Slight |
| **KNeighborsClassifier** | 0.7796 | ±0.0054 | ❌ Severe |

### 4. Results
- **RandomForest** and **GradientBoosting** both achieve ~**79.7% CV accuracy**
- RandomForest generalizes best with minimal train-test gap
- GradientBoosting slightly overfits but still strong
- KNN severely overfits despite tuning

## 🚀 Usage

```bash
pip install -r requirements.txt
jupyter notebook "project-spaceship-titanic.ipynb"
```

## 📁 Repository Structure

```
project-spaceship-titanic/
├── project-spaceship-titanic.ipynb   # Main notebook
├── train.csv                          # Training data
├── README.md
├── requirements.txt
└── .gitignore
```
