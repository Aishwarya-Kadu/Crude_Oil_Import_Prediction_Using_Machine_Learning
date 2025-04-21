# ML_Based_Crude_Oil_Import_Predictor
Machine learning model to forecast crude oil import volumes based on historical data and key economic indicators.

## Contents

- Project Overview
- Tools
- Data Overview
- Data Preprocessing
- Exploratory Data Analysis


## Project Overview
Crude oil is one of the world's most significant commodities, influencing energy policy, international trade, and financial markets. Many countries depend on crude oil imports to meet national energy demands, and successful importation strategies are thus key to economic stability. The objective of this project is to analyze Canada's import trends for crude oil using historical data to uncover trends, identify key trading partners, and support evidence-based business and policy decisions. The motivation for this project is the strategic importance of crude oil to Canada's energy security and economy. Despite being one of the leading oil producers in the world, Canada still imports massive volumes of crude oil specifically to meet regional demands in Eastern provinces where domestic supply access is hindered by infrastructure and logistical constraints. The impetus for the project was increasing volatility in crude oil prices and its impact on national economies. With geopolitical tensions, supply chain disruptions, and environmental concerns affecting global oil trade, it is important to develop data-driven insights that can help stakeholders respond to them effectively. With the utilization of past data and current market trends, the project plans to provide effective recommendations to enterprises, policymakers, and financial analysts.

The core business question addressed in this project are as follows: 

1. How can predictive analytics be used to forecast crude oil import volume and associated costs to improve planning, budgeting, and procurement decisions.
2. What are the key factors influencing crude oil prices?
3. What role do macroeconomic and economic (trade level) factors play in shaping oil import strategies? 

## Tools
- Microsoft Excel
- Python

## Data Overview
The dataset used in this project was carefully compiled from multiple reliable sources, primarily focused on macroeconomic indicators, oil production and import trends, and energy-related financial metrics. The aim was to create a comprehensive view of Canada's crude oil import landscape, incorporating both economic and energy-specific variables.

The data spans from 1960 to 2024 and includes features such as:
- GDP (USD)
- Per Capita Income (USD)
- Inflation Rate
- Population
- Real Interest Rate
- Government Net Lending/Borrowing (as a percentage of GDP)
- Canada's Current Account Balance (USD)
- Crude Oil Production (Cubic Meters)
- Crude Oil Imports (Cubic Meters)
- Crude Oil Import Cost (USD)
- Canada’s Crude Oil Refining Capacity (Cubic Meters)


|Columns|Description|
|-------|-----------|
|GDP (USD)|Gross Domestic Product represents the total monetary value of all goods and services produced within Canada’s borders over a specific period. It is a key indicator of the country’s overall economic performance and health.|
|Per Capita Income (USD)|This measures the average income earned per person in a given year, calculated by dividing GDP by the total population. It provides insights into the standard of living and economic well-being of individuals.|
|Inflation Rate|The rate at which the general level of prices for goods and services rises over time, leading to a decline in purchasing power. It is usually expressed as a percentage on an annual basis.|
|Population|The total number of people living in Canada during a given year. This variable can influence both consumption and production levels and is essential for calculating per capita measures.|
|Real Interest Rate|The interest rate adjusted for inflation, reflecting the true cost of borrowing. It impacts consumer spending, investments, and savings behavior in the economy.|
|Government Net Lending/Borrowing (as a percentage of GDP)|This metric shows the fiscal balance of the government relative to the size of the economy. A positive value indicates a surplus, while a negative value indicates a deficit.|
|Canada's Current Account Balance (USD)|This reflects the net value of Canada's transactions with the rest of the world, including trade in goods and services, income, and current transfers. A surplus or deficit here can influence currency stability and trade policies.|
|Crude Oil Production (Cubic Meters)|The total volume of crude oil extracted within Canada in a given year. It’s a direct indicator of domestic oil supply and plays a critical role in national energy strategy.|
|Crude Oil Imports (Cubic Meters)|The volume of crude oil imported into Canada from foreign sources. This variable is crucial for understanding energy dependence and foreign trade dynamics.|
|Crude Oil Import Cost (USD)|Represents the total monetary cost, in U.S. dollars, incurred for importing crude oil during a specific time period. This includes expenses related to the purchase of crude oil, transportation, tariffs, and other associated import charges.|
|Canada’s Crude Oil Refining Capacity (Cubic Meters)|The total volume of crude oil that Canadian refineries can process annually. This determines the country's ability to convert raw crude into usable petroleum products like gasoline and diesel.|

## Data Preprocessing
All data cleaning and preprocessing tasks were carried out using Microsoft Excel and Python. The process involved handling missing values by either removing rows with insufficient data or imputing reasonable estimates where applicable. Data types were standardized, including parsing date fields into a consistent datetime format and converting currency figures into numeric values for accurate analysis. Additionally, efforts were made to verify consistency in units across all years and data sources, ensuring that comparisons and calculations remained valid throughout the dataset.

## Exploratory Data Analysis

To understand the characteristics of the dataset, we performed exploratory data analysis (EDA) and visualized key features using **histograms**. These plots helped us examine the distributions and identify potential skewness, trends, and outliers that could impact model performance.

![image](https://github.com/user-attachments/assets/99e754ac-a3a8-4730-9160-af5a120a7857)


![image](https://github.com/user-attachments/assets/666e0aa5-a379-41ec-a452-477abd81b13c)


![image](https://github.com/user-attachments/assets/d6d32911-df72-4ccd-92d1-dea2d305c4e8)

### Crude Oil Production, Import Volume & Import Cost

- All three features show **positive skewness**, with most values concentrated at the lower end and a few significant outliers on the higher end.
- This indicates that in most years, Canada's crude oil activities were relatively moderate, but a few years saw unusually high production, import volume, or import costs.
- These spikes may be attributed to **geopolitical events**, **global demand surges**, or **price fluctuations**.


### GDP (USD)

- The **GDP distribution** is also **positively skewed**, reflecting generally modest economic growth with a few standout years of high GDP.
- These peaks could be linked to **economic booms** or **global oil price increases** that positively impacted Canada’s economy.




### Population

- The population shows a nearly **uniform distribution**, suggesting **steady and predictable growth** over the years with no major spikes or drops.

### Crude Oil Refining Capacity

- Displays a **bimodal distribution**, indicating **two distinct periods of growth or investment** in refining infrastructure.
- These phases may be associated with **policy changes**, **technological upgrades**, or **shifts in demand** for refined oil products.

### Insights for Modeling

- Understanding these distributions helped inform our **feature selection**, **data normalization**, and **outlier handling** strategies.
- The presence of outliers and skewness highlights the importance of **robust model training**, especially in time series and regression tasks.


## Methodology
The methodology adopted in this project involves a structured approach to data preprocessing, exploratory analysis, model training, and evaluation to predict oil import volume and cost based on economic and production indicators. The steps outlined below detail the implementation process using Python and machine learning libraries.

The initial step in the implementation involved importing the necessary Python libraries required for data analysis, visualization, and machine learning. Key libraries such as pandas and numpy were used for data manipulation, matplotlib and seaborn for data visualization, and scikit-learn and xgboost for building and evaluating predictive models.

![image](https://github.com/user-attachments/assets/073ee590-dbf0-4db6-a577-9fe3bf9ac922)

The dataset was loaded using pandas.read_excel() and verified with .head() to inspect the first five rows and understand its structure.

![image](https://github.com/user-attachments/assets/2fd09338-cd92-4bdd-bd4c-b9444182c22b)

To gain a deeper understanding of the dataset’s structure and statistical properties, the describe () function was utilized. This function provided summary statistics such as mean, standard deviation, minimum, maximum, and quartile values for the numerical columns, which helped in identifying patterns, ranges, and potential outliers in the data.

![image](https://github.com/user-attachments/assets/c5ceea27-02c9-465c-a160-b08dbadd4005)

To ensure each column was correctly interpreted, the data types of all variables were examined using the dtypes attribute. This step was essential to confirm the format of the data and to identify any necessary conversions before further processing.

![image](https://github.com/user-attachments/assets/2b26eba5-c8d9-48e3-88c4-b10455069793)

Although the dataset had been pre-cleaned using Excel, we performed an additional check for any missing or null values using the isnull().sum() function in Python. This step ensured the integrity of the data before moving forward with analysis.

![image](https://github.com/user-attachments/assets/a7a6769e-3eaf-4d74-ae24-97cfbb6f5da8)

To visually explore the relationships between all numerical variables in the dataset, we used the pairplot() function from the Seaborn library. This helped us identify potential correlations, patterns, and any outliers that might impact model performance.

![image](https://github.com/user-attachments/assets/d62fd353-1c90-4213-8c7e-909f43be4603)

A correlation heatmap was created using Seaborn to visualize relationships between variables. GDP showed strong positive correlations with Per Capita Income, Crude Oil Production, Population, Import Cost, and Refining Capacity; indicating economic growth aligns with energy and income metrics. In contrast, Inflation Rate and Real Interest Rate had weak or negative correlations with most variables. Notably, Crude Oil Imports and Import Cost were highly correlated, highlighting potential multicollinearity. This analysis helped guide feature selection for modeling.

![image](https://github.com/user-attachments/assets/46db122c-e91e-4b0b-a01c-e40a226ac281)

We selected Crude Oil Import Volume and Import Cost as target variables due to their relevance in assessing Canada’s oil dependency. The dataset was split 70-30 for training and testing. Two models Random Forest and XGBoost were used for prediction, chosen for their accuracy and ability to handle complex data. Model performance was evaluated using MAE and R² on the test set to assess generalizability.

![image](https://github.com/user-attachments/assets/7de24bc9-e8dc-4b82-9d97-a8994c18d0f4)

The models showed high RMSE and MAE due to the large scale of the target variables, but this doesn't imply poor performance. With R² scores of 0.846 (Random Forest) and 0.798 (XGBoost), both models effectively explained most of the variance, highlighting that relative error is more meaningful than absolute error in this context.

![image](https://github.com/user-attachments/assets/eb8304e4-5150-4518-84a0-d6a5e11a96bd)

Scatter plots comparing actual vs. predicted values showed a strong positive linear trend for both models, indicating good prediction accuracy. Random Forest exhibited slightly tighter clustering than XGBoost, suggesting better performance. These visuals support the evaluation metrics and confirm the models’ reliability.

|Oil Import Volume|Oil Import Cost|
|-----------------|---------------|
|![image](https://github.com/user-attachments/assets/15606d07-0e82-4559-9299-d6430417b5b1)|![image](https://github.com/user-attachments/assets/f09b5d3f-33fc-4511-aa7c-959efc4b0bed)|
|![image](https://github.com/user-attachments/assets/38161b73-2e51-4cf9-a1ee-0ba646619b95)|![image](https://github.com/user-attachments/assets/3ec8a1b2-8c19-4eee-a7b0-7d79250bf7ac)|

The Random Forest learning curve shows consistently low training error and steadily decreasing cross-validation error, indicating improved generalization with more data. This pattern confirms the model is reliable, well-fitted, and not overfitting.

![image](https://github.com/user-attachments/assets/5f0c6bde-6f0f-4997-9030-71ad2e879e9a)

![image](https://github.com/user-attachments/assets/f4989001-e609-41d1-a200-6e5e948f87c7)





