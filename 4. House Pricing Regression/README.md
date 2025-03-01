<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/4.%20House%20Pricing%20Regression/House.jpg" alt="image alt" width="500" height="420">
</div>

## 📊 **4. House Pricing Regression**

### 🔍 **Overview**

This project demonstrates the power of data-driven decision-making in real estate pricing. By leveraging machine learning techniques, a predictive model was developed to enhance pricing accuracy, operational efficiency, and investment decision-making at Cuckoo Cribs Corporation. The model was designed to replace subjective pricing methods with a systematic, data-backed approach, ensuring consistency and reliability. The best-performing model was selected after testing multiple regression techniques, leading to the development of a "pricing machine" for real estate agents.

### 🛠️ **Tools & Technologies**

- **KNIME Analytics Platform**: Used for data preprocessing, model training, and evaluation.
- **Regression Models**: Random Forest, Gradient Boosted Trees, and Polynomial Regression were tested.
- **KNIME Nodes Used**: Rule Engine, String to Number, Partitioning, Correlation Filter, Min-Max Normalization, and various visualization nodes.

### 📂 **Dataset**

The dataset comprises 1,460 rows and 80 variables related to house pricing. Exploratory data analysis was conducted using scatter plots and bar charts.
Key preprocessing steps included:

- Handling Missing Values – Converted "NA" entries to empty values and applied mean/mode imputation
- Feature Selection – Removed highly correlated variables (threshold: 0.8) while retaining GarageArea for its predictive importance
- Data Splitting & Normalization – Applied a 70/30 partition on training data and Min-Max Normalization for consistency


### 🚀 **Key Findings**



Key Findings

Best Model Selection – After rigorous testing, the best-performing regression model was chosen based on accuracy, interpretability, and computational efficiency.

Deployment Strategies:

- User-Friendly Dashboard – An interactive interface where agents can input property details and receive price predictions
- Mobile Application – A proposed app to provide instant property valuations and alerts on undervalued listings

Practical Applications for Real Estate Agents:

- Identifying Investment Opportunities – Using price predictions to spot undervalued properties and assess potential appreciation.
- Accurate Price Determination – Ensuring competitive property pricing to attract buyers quickly and increase transaction efficiency.
- Market Segmentation & Targeting – Leveraging data to refine marketing strategies and personalize property recommendations.
