# Airline Customer Satisfaction Classifier ✈️
This project focuses on predicting airline customer satisfaction using supervised machine learning algorithms. The dataset includes various features related to in-flight and on-ground services, and the goal is to classify whether a passenger is **satisfied** or **neutral/dissatisfied**.

## How to Run
1. Upload `train.csv`and `test.csv` to your environment (this project was made using Google Colab)
2. Run all cells in the notebook
3. Modify or expand classifiers and visualizations as needed

## Dataset
Airline Passenger Satisfaction from Kaggle: https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction
The dataset was composed of two files: `train.csv` and `test.csv`.
### Key Features:

- Inflight wifi service  
- Online boarding  
- Seat comfort  
- Leg room service  
- Baggage handling  
- Inflight entertainment  
- Cleanliness  
- Food and drink  
- Gate location  
- and more...

The target column is:
- `satisfaction`: with values `satisfied` or `neutral or dissatisfied`.

## Preprocessing

- Merged `train.csv` and `test.csv` into `CombinedLab.csv`
- Removed missing values
- Removed unnecessary columns such as `id` and `Unnamed: 0`
- Created two new features:
  - `avg_rating`: average of all service-related ratings
  - `avg_rating_services_on_board`: average of onboard service ratings

## Encoding & Scaling

- Categorical features were encoded using **OneHotEncoder** from `category_encoders`
- Features were standardized using **StandardScaler** and **RobustScaler**
- Dimensionality reduction using **PCA** for visualization

## Models

### 1. Naive Bayes (GaussianNB)

- Trained on scaled features
- Accuracy (Test Set): ~56.3%
- ROC AUC: ~0.6352
- Cross-validated ROC AUC (5-fold): ~0.6407
- Evaluation metrics included: Accuracy, Precision, Recall, Confusion Matrix, ROC Curve

### 2. Decision Tree Classifier

- Trained with both full feature set and reduced feature set (onboard services only)
- Tuned using parameters like `max_depth`, `min_samples_leaf`, `min_samples_split`
- Visualized using `Graphviz`

## Evaluation Metrics

- Accuracy  
- Null Accuracy  
- Confusion Matrix  
- Classification Report  
- ROC Curve  
- ROC AUC Score  
- Cross-validation (10-fold)  
- Histogram of predicted probabilities  

## Tools and Libraries

- Python (Google Colab)
- Pandas, NumPy, Matplotlib, Seaborn
- scikit-learn (PCA, Naive Bayes, DecisionTreeClassifier, metrics)
- category_encoders
- graphviz

This project was developed as part of an academic course.
