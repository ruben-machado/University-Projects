<img align="right" src="https://github.com/ruben-machado/University-Projects/blob/9b8ade999e3a5061a855d847813c9240332cac77/Nova%20IMS%20logo" alt="image alt" width="90" height= "90"> <br>

# University Projects  

## A collection of projects done during my master's degree

## Index

### **1. Budgeting for the future**

### 🔍 **Overview**
This project aims to enhance the participatory budgeting process in Mining City through data-driven insights. By understanding residents' demographics and lifestyle preferences, the city council seeks to improve citizen engagement and optimize resource allocation. Using predictive modeling techniques, the goal is to classify residents into key lifestyle segments such as 'Travel Enthusiast,' 'Health-Conscious,' and 'Investor' to support data-informed decision-making. The project involves identifying relevant variables, implementing multiclass classification models, and optimizing predictions using the weighted F1 Score.

### 🛠️ **Tools & Technologies**

#### **Programming Language:**
- Python
#### **Libraries/Frameworks:**
- **Data Manipulation & Analysis**:
  - `pandas`
  - `numpy`
- **Data Visualization**:
  - `matplotlib.pyplot`
  - `seaborn`
  - `plotly.express`
- **Machine Learning**:
  - `scikit-learn` (includes: `KNNImputer`, `SimpleImputer`, `MinMaxScaler`, `LabelEncoder`, `StandardScaler`, `LinearRegression`, `LassoCV`, `LogisticRegression`, `RidgeClassifier`, `RFE`, `SelectKBest`, `train_test_split`, `KFold`, `RandomizedSearchCV`, `StratifiedKFold`, `GridSearchCV`, `DecisionTreeClassifier`, `RandomForestClassifier`, `GradientBoostingClassifier`, `StackingClassifier`, `KNeighborsClassifier`, `PCA`, `accuracy_score`, `confusion_matrix`, `precision_score`, `recall_score`, `ConfusionMatrixDisplay`, `f1_score`, `classification_report`, `roc_curve`, `auc`, `make_scorer`)

### 📂 **Dataset**

The dataset consists of citizen records with descriptive attributes available in both the training and test sets. The training set includes labeled data to build and validate machine learning models, while the test set contains similar attributes without the target variable. The goal is to predict lifestyle segments using these features, ensuring the target variable is not used as an input for model training.
