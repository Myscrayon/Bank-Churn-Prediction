# Bank Customer Churn Prediction

A machine learning project predicting bank customer churn, with a focus on **handling class imbalance** using four different strategies: baseline, `class_weight='balanced'`, `RandomForestClassifier` and `Tuned class_weight`.

## 📊 Dataset

- **Samples**: 10,000 customer records
- **Features**: 11 (age, tenure, credit, salary, city, gender, etc.)
- **Target**: Binary classification (Exited: 0 = retained, 1 = churned)
- **Class Balance**: ~20.4% churned / ~79.6% retained → **imbalanced**

## 🚀 Project Workflow

1. **Exploratory Data Analysis (EDA)**
   - Target distribution, boxplots, grouped churn rates
2. **Data Preprocessing**
   - Drop ID column, One-Hot encode `City`, oridinal encode `Gender`
3. **Train/Test Split**
   - 80/20 with `stratify=y` to preserve class ratio
4. **Modeling with Three Imbalance-Handling Strategies**
   - **Baseline**: no handling
   - **Method 1**: `class_weight='balanced'`
   - **Method 2**: `RandomForestClassifier`
   - **Method 3**: `Tuned class_weight`
5. **Hyperparameter Tuning**
   - `GridSearchCV` with `roc_auc` scoring, 5-fold CV
6. **Threshold Tuning**
   - Precision-Recall curve to balance recall/precision trade-off
7. **Model Comparison & ROC Visualization**

## 📈 Results

| Method | AUC | Recall (Churn) | F1 (Churn) |
|--------|-----|----------------|------------|
| Baseline | 0.7391 | 0.1769 | 0.2717 |
| class_weight='balanced' | 0.7606	 | 0.6536 | 0.4776 |
| RandomForestClassifier | 0.7618 | 0.6781 | 0.4859 |
| Tuned class_weight | 0.8525 | 0.6192 | 0.5993 |


**Conclusion**:  `class_weight`  improves recall for the minority class, with trade-offs between precision and recall.

## 🖼️ Visualizations Included

- Target distribution (bar + pie)
- Boxplots: numerical features vs churn
- Grouped churn rate: gender / city
- Correlation heatmap
- ROC curves comparison (5 models)
- Precision-Recall curve with multiple thresholds
- Feature importance (Random Forest)
- Confusion matrix

## 📦 Installation

```bash
git clone https://github.com/Myscrayon/Bank-Churn-Prediction.git
cd churn-prediction
pip install -r requirements.txt
```

## 📁 File Structure

```
├── Churn_Prediction.ipynb   # Main notebook
├── README.md                # brief introduction
├── requirements.txt         # Dependencies
├── BankCustomer.xlsx        # Data
├── churn_model.pkl          # model
└── images/                  # saved plots
```

## 👨‍💻 Author :  Myscrayon