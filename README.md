# Predictive Maintenance Model for Textile Machinery

## 📌 Project Overview
Unexpected machinery breakdowns cause severe operational downtime and cost. This project builds a predictive maintenance pipeline that uses sensor readings to classify whether a machine is likely to fail, shifting from reactive repairs to proactive maintenance.

**Dataset:** [Machine Predictive Maintenance Classification](https://www.kaggle.com/datasets/shivamb/machine-predictive-maintenance-classification) (Kaggle), 10,000 machine sensor records. This is snapshot sensor data, not a time-series — each row is an independent reading with no sequential/timestamp dependency.

## 🚀 Key Achievements

- **Class-Imbalance-Aware Evaluation:** The failure class is rare (~3.4% of records). Rather than reporting plain accuracy — which a "predict nothing" model could nearly match at ~96.6% — this project evaluates precision and recall specifically on the failure class.
- **Model Comparison:** Trained both Random Forest and XGBoost classifiers. XGBoost outperformed Random Forest, achieving **75% recall and 91% precision** on the failure class (vs. Random Forest's 65% recall, 88% precision).
- **Real-World Impact:** XGBoost correctly caught 51 of 68 real failures in the test set, with only 5 false alarms out of 1,932 healthy machines.
- **Feature Importance:** Identified **Torque** and **Air Temperature** as the top two failure-driving sensor readings, guiding which sensors deserve the highest monitoring priority.

## 📊 Feature Importance
![Feature Importance](feature_importance.png)

## 🛠️ Tech Stack
- **Language:** Python
- **Machine Learning:** Scikit-learn (Random Forest), XGBoost Classifier
- **Data Processing & Visualization:** Pandas, Matplotlib, Seaborn

## 🔭 Next Steps
- Apply class-balancing techniques (SMOTE, class weighting) to test whether recall on the failure class can be further improved
- Extend to multi-class prediction using the dataset's specific `Failure Type` labels
- Deploy as a real-time scoring pipeline on streaming sensor data
