## 📊 **5. Hotel Cancellation Prediction**

### 🔍 **Overview**

This project applies a data-driven approach to predict hotel cancellations for the Lorem Ipsum Hotel Group, enabling proactive decision-making and improved revenue management. By leveraging historical booking data, the goal was to develop predictive models that help optimize resource allocation and minimize revenue losses caused by last-minute cancellations. Using KNIME, data preprocessing techniques were applied, followed by model training and evaluation. The findings provide actionable insights to enhance business sustainability and customer satisfaction. Regular model updates and financial impact analysis are recommended to maintain accuracy and optimize outcomes. This approach aims to balance operational efficiency with an improved guest experience.

### 🛠️ **Tools & Technologies**

- **Software**: `KNIME` (used for data preprocessing, model training, and evaluation)
- **KNIME Nodes Used**: Data preprocessing (CSV Reader, String Replacer, String to Number), visualization (various descriptive statistics and chart nodes), model training, evaluation (Scorer, Confusion Matrix, Binary Classification Inspector)
- **Machine Learning Models**: Decision Tree and Random Forest

### 📂 **Dataset**

The dataset comprises 72,646 rows and 25 variables related to hotel cancellations. Two datasets were provided: Hotel_Data for training and Hotel_Test_Data for testing. Data preprocessing included handling missing values, transforming data types, and normalizing variables to enhance model performance. Feature selection involved removing highly correlated or irrelevant variables to improve prediction accuracy.

### 🚀 **Key Insights**

- The Decision Tree model achieved an accuracy of 81.05%, slightly outperforming the Random Forest model (80.619%).
- The ROC AUC metric was used to evaluate model performance, revealing that the Decision Tree had superior classification capabilities.
- A cost-benefit analysis of false positives (missed cancellations) and false negatives (incorrect cancellations) is recommended to optimize model sensitivity.
- Continuous monitoring and model updates are crucial to maintaining predictive accuracy, incorporating new features such as guest reviews and booking behaviors.
- Implementing a data-driven cancellation management strategy can enhance revenue management, optimize resource allocation, and improve guest satisfaction.
