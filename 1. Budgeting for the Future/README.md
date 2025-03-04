## 📊 **1. Budgeting for the future**

### 🔍 **Overview**
This project aims to enhance the participatory budgeting process in Mining City through data-driven insights. By understanding residents' demographics and lifestyle preferences, the city council seeks to improve citizen engagement and optimize resource allocation. Using predictive modeling techniques, the goal is to classify residents into key lifestyle segments such as Travel Enthusiast, Health-Conscious, and Investor to support data-informed decision-making. The project involves identifying relevant variables, implementing multiclass classification models, and optimizing predictions using the weighted F1 Score.

Note: This group project was developed in an academic context as part of the Data Mining II course. The data was provided by the professors.

### 🛠️ **Tools & Technologies**

#### **Programming Language**: `Python`

#### **Libraries/Frameworks:**
- **Data Manipulation & Analysis**: `pandas`,`numpy` 
- **Data Visualization**: `matplotlib.pyplot`, `seaborn`,`plotly.express`
- **Machine Learning**: `scikit-learn` (includes: `KNNImputer`, `SimpleImputer`, `MinMaxScaler`, `LabelEncoder`, `StandardScaler`, `LinearRegression`, `LassoCV`, `LogisticRegression`, `RidgeClassifier`, `RFE`, `SelectKBest`, `train_test_split`, `KFold`, `RandomizedSearchCV`, `StratifiedKFold`, `GridSearchCV`, `DecisionTreeClassifier`, `RandomForestClassifier`, `GradientBoostingClassifier`, `StackingClassifier`, `KNeighborsClassifier`, `PCA`, `accuracy_score`, `confusion_matrix`, `precision_score`, `recall_score`, `ConfusionMatrixDisplay`, `f1_score`, `classification_report`, `roc_curve`, `auc`, `make_scorer`)

### 📂 **Dataset**

The dataset consists of citizen records with descriptive attributes available in both the training and test sets. The training set includes labeled data to build and validate machine learning models, while the test set contains similar attributes without the target variable. The goal is to predict lifestyle segments using these features, ensuring the target variable is not used as an input for model training.

### 🔍 **Data Exploration & Preprocessing**

The dataset was analyzed for correlations, distribution, and inconsistencies. Highly correlated features were removed, and categorical variables were transformed. Outliers and missing values were addressed using appropriate statistical methods. Data normalization and feature engineering were applied to enhance model performance, ensuring the dataset was clean and structured for classification.

### 🤖 **Multiclass Classification**
#### 🎯 **Feature Selection**

Feature selection was conducted using multiple techniques, including Recursive Feature Elimination, LASSO, ANOVA, and Random Forest. A subset of features that consistently demonstrated importance was selected to improve interpretability and model efficiency.

#### 📈 **Modeling & Performance Evaluation**

Several machine learning models were tested, including Decision Tree, Logistic Regression, Random Forest, Gradient Boosting, K-Nearest Neighbors, and Stacking Classifier. Cross-validation was used to ensure robust performance evaluation, and MinMax Scaling was applied to standardize features.

### 🚀 **Key Findings & Next Steps**

- Feature selection improved model interpretability and reduced complexity
- The Stacking Classifier provided the most accurate predictions by leveraging multiple models
- Future improvements include further hyperparameter tuning and testing additional ensemble techniques
