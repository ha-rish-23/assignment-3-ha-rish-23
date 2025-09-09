# Assignment-3 DAL (DA5401)

| Field           | Detail                  |
|-----------------|--------------------------|
| Name            | Harish B                |
| Roll Number     | DA24S024              |
| Course          | DA5401 – Data Analytics Lab|
| Assignment | 3          |

## Credit Card Fraud Detection using Clustering-based Approaches for Class Imbalance

## 📁 Folder Structure

```
assignment-3-ha-rish-23/
│
├── data/
│   └── creditcard.csv
├── clustering.ipynb
├── README.md
```

- `data/`: Contains the credit card fraud dataset (`creditcard.csv`).
- `clustering.ipynb`: Main Jupyter notebook with all code, analysis, and visualizations.
- `README.md`: Project overview and documentation.

---

## 📝 Overview

This assignment explores advanced **clustering-based resampling techniques** for handling class imbalance in credit card fraud detection. The project compares five different approaches to address the severe class imbalance (578:1 ratio) in the dataset:

1. **Baseline Model**: Logistic regression on imbalanced data
2. **SMOTE**: Synthetic Minority Oversampling Technique
3. **CBO**: Clustering-Based Oversampling
4. **CBU-Proportional**: Clustering-Based Undersampling with proportional selection
5. **CBU-Proximity**: Clustering-Based Undersampling with proximity-based selection

The workflow includes comprehensive evaluation using precision, recall, F1-score, and AUC-ROC metrics, along with creative visualizations to compare model performance and business impact.

---

## 📚 Key Learnings

### 1. Class Imbalance Problem

- Credit card fraud datasets exhibit severe class imbalance (284,315 non-fraud vs 492 fraud cases)
- Traditional accuracy metrics are misleading - a model predicting all transactions as non-fraud would achieve 99.83% accuracy
- Precision, recall, and F1-score are more meaningful metrics for imbalanced datasets

### 2. Clustering-Based Approaches

- **CBO (Clustering-Based Oversampling)**: Clusters minority class into subgroups, then applies SMOTE to each cluster separately to preserve data patterns
- **CBU (Clustering-Based Undersampling)**: Clusters majority class and strategically removes instances while preserving representative samples
- Clustering approaches outperform naive SMOTE by preserving natural data structure and avoiding boundary issues

### 3. Model Performance Comparison

- **Baseline**: High precision (0.8750) but poor recall (0.3673) - misses 63% of fraud cases
- **SMOTE**: High recall (0.9286) but low precision (0.0738) - too many false alarms
- **CBO**: Balanced performance with good recall (0.9184) and better precision (0.0888)
- **CBU-Proximity**: Best overall performance with optimal F1-score (0.1645) and balanced precision-recall trade-off

---

## 🔍 Key Insights

### Technical Advantages of Clustering Approaches:
- **Pattern Preservation**: Maintains natural data relationships better than naive oversampling
- **Data Structure Awareness**: Recognizes inherent subgroups within classes
- **Boundary Safety**: Avoids creating synthetic samples near decision boundaries
- **Computational Efficiency**: CBU methods reduce dataset size while improving performance

### Business Impact:
- **CBU-Proximity** achieves the best balance for fraud detection applications
- Reduces computational costs compared to oversampling methods
- Lower operational costs due to balanced performance
- Suitable for production deployment with manageable false alarm rates

---

## � Visualizations

The notebook includes comprehensive visualizations:
- **Radar Chart**: Comparing SMOTE vs clustering capabilities across 4 dimensions
- **Performance Heatmap**: Color-coded comparison of all metrics across models
- **Dataset Size Pie Chart**: Computational efficiency comparison
- **Business Impact Chart**: Real-world implications comparison
- **Combined Metrics Bar Chart**: All performance metrics in a single view

---

## 🏆 Final Recommendation

**Winner: CBU with Proximity-Based Selection**
- **F1-Score**: 0.1645 (Highest)
- **Recall**: 81.6% (Good fraud detection)
- **Precision**: 0.0932 (Manageable false alarms)  
- **Dataset Size**: 114,739 samples (Most efficient)

This method achieves the optimal balance between fraud detection capability and false alarm management, making it the most suitable approach for production deployment.

---

## 🚀 How to Run

1. **Download the dataset**: 
   - Download `creditcard.csv` from [Kaggle Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
   - Place the file in the `data/` folder: `data/creditcard.csv`
   - Note: The dataset is ~144MB and excluded from git due to size limitations
   
2. Open `clustering.ipynb` in Jupyter or VS Code
3. Run all cells sequentially to reproduce the complete analysis and visualizations
4. The notebook is structured following the assignment requirements with clear sections for data exploration, model implementation, and comparative analysis

## 📋 Prerequisites

- Python 3.x
- Required packages: `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `imbalanced-learn`
- Jupyter Notebook or VS Code with Python extension