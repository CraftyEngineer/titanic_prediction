# 🚢 Titanic - Machine Learning from Disaster

Welcome to my solution for the **Titanic - Machine Learning from Disaster** Kaggle competition!  
In this project, I built multiple models to predict passenger survival based on various features such as age, gender, class, family size, and more.
Ranked 3800 out of 15985

---

## 🧠 Objective

The goal of this notebook is to predict whether a passenger survived the Titanic disaster using the provided dataset. This is a classic **binary classification problem**, where the target variable is:

- `Survived` = `0` (Did not survive)
- `Survived` = `1` (Survived)

---

## 📁 Dataset Used

- `train.csv` – Training data used for model training and validation
- `test.csv` – Data for which survival prediction is required

---

## 🧹 Data Preprocessing & Feature Engineering

Before building the models, I performed the following preprocessing steps:

### 🔧 Cleaning and Encoding:
- Converted **Sex** to numerical (`male` = 0, `female` = 1)
- Converted **Embarked** values to numerical (`S` = 0, `C` = 1, `Q` = 2)
- Filled missing values in **Age** using **Title-based median age imputation**
- Created **Title** feature from the passenger’s name
- Created **HasCabin** feature to indicate cabin info presence
- Created **FamilySize** = `SibSp + Parch + 1`
- Created **IsAlone** = 1 if `FamilySize == 1` else 0
- Applied **StandardScaler** to scale all features

---

# 📊 Model Performance & Evaluation Summary

---

## 🔹 1. SVM Classifier

- 🔥 **Training Accuracy:** 79.07%  
- 🧪 **Validation Accuracy:** 78.77%  
- 🧾 **Kaggle Test Score:** 77.511%

## 🔹 2. Random Forest

- 🔥 **Training Accuracy:** 87.22% 
- 🧪 **Validation Accuracy:** 78.77%  
- 🧾 **Kaggle Test Score:** 77.511%

## 🔹 3. XGBoost Classifier 🥇

- 🔥 **Training Accuracy:** 86.10% 
- 🧪 **Validation Accuracy:** 81.01% 
- 🧾 **Kaggle Test Score:** 77.990%
✅ This gave the best public score out of all models!

## 🔹 4. Neural Network (Keras Sequential)

- 🔥 **Training Accuracy:** 86.23% 
- 🧪 **Validation Accuracy:** 82.68% 
- 🧾 **Kaggle Test Score:** 77.511%
(Yes, despite high val accuracy, public score stayed the same – likely due to overfitting or data distribution shift)

---

## 📈 Evaluation Strategy
- Used train_test_split with stratify=Y to maintain class balance.
- Evaluation metric: Accuracy
- Predicted test results saved as: titanic_<model>_test_predictions.csv

---

## 📊 Summary Table

| Model           | Training Acc | Validation Acc | Kaggle Score |
|----------------|--------------|----------------|--------------|
| SVM            | 79.07%       | 78.77%         | 77.511%      |
| Random Forest  | 87.22%       | 78.77%         | 77.511%      |
| Neural Network | 86.23%       | 82.68%         | 77.511%      |
| XGBoost        | 86.10%       | 81.01%         | 🥇 77.990%    |

---

## 🧠 Lessons Learned
- Simpler models like SVM and Random Forest can perform well with good feature engineering.
- More complex models like Neural Nets may overfit without careful tuning.
- XGBoost consistently delivers strong results for tabular data.
- Public leaderboard performance doesn't always align with validation accuracy!
  
---

## 🛠 Future Improvements
- Use cross-validation instead of a single train/val split
- Tune hyperparameters (e.g., using GridSearchCV or Optuna)
- Try ensemble techniques (stacking/blending)
- Handle outliers and apply PCA for dimensionality reduction

---
## 💬 Feedback?
Have suggestions or questions?
Feel free to open an issue or message me!

---

## ⭐ Credits
Huge thanks to Kaggle and the Titanic dataset contributors.
Notebook created with ❤️ by CraftyEngineer

---

## 📎 License
This repository is open source and available under the MIT License.
