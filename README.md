# <p align="center" dir="auto">Employee Turnover Prediction</p>
## <p align="center" dir="auto">Using Machine Learning to Optimize Employee Retention</p>
<div align="center">
<img src="https://github.com/user-attachments/assets/3d60cda8-f6b9-47fc-b195-7bf7f1dd7ff4" width="700" />
</div>

# 1. Business Problem

## 1.1. Dataset
This project utilizes a **publicly available dataset** from a fictional company, covering employee records from **2006 to 2020**. The dataset includes over 300 records with details such as:

- **Employee demographics**: Age, gender, marital status, and ethnicity.
- **Job information**: Department, position, and hiring source.
- **Compensation**: Salary, pay raises, and performance reviews.
- **Engagement and behavior**: Absenteeism, satisfaction levels, and punctuality.
- **Turnover status**: Employment duration, termination date, and reasons for leaving.

The dataset provides a comprehensive view of the workforce, enabling us to analyze historical trends, uncover critical turnover drivers, and build a robust predictive model.  
Dataset source: [https://www.kaggle.com/datasets/rhuebner/human-resources-data-set]


## 1.2. Problem to be Solved
Employee turnover has been a persistent challenge for organizations, leading to significant financial and operational impacts. A recent analysis revealed that the average cost of replacing an employee, including recruitment, onboarding, and productivity loss, 
amounts to **R$ 20.000 per employee**. For a mid-sized company experiencing a turnover rate of 15% annually, this translates to millions in recurring expenses.

The company is determined to address this issue by identifying the key factors driving turnover and implementing predictive measures. The primary goal of this project is to:

1. **Identify the root causes of employee turnover** through data-driven insights.
2. **Predict which employees are at risk of leaving** using machine learning models.
3. Enable HR teams to take proactive actions to improve employee retention, reduce costs, and enhance overall organizational performance.

# 2. Business Assumptions

To conduct this analysis effectively, the following assumptions were made:

1. **Reference Date**:  
   All analyses assume that the current date is **01/01/2020**, aligning with the publication year of the dataset. This reference date ensures consistency when calculating metrics such as tenure and time since specific events.

2. **Turnover Definition**:  
   For the purpose of turnover prediction, no distinction was made between **voluntary turnover** (employee-initiated) and **involuntary turnover** (company-initiated). Both scenarios were treated uniformly to simplify the modeling process and focus on identifying overall employee exit risks. 

By adopting these assumptions, the project aims to provide actionable insights and a predictive framework that addresses turnover holistically, regardless of its underlying cause.

# 3. Solution Strategy

The approach to solve the problem of employee turnover prediction and analysis involved the following steps:

1. **Data Cleaning**:  
   Ensured the dataset was clean and ready for analysis by handling missing values, removing duplicates, and standardizing data formats. This step established a robust foundation for subsequent processes.

2. **Feature Engineering**:  
   Created new features to better capture the characteristics of employee behavior and organizational patterns, such as tenure, time in current position, and performance trends.

3. **Exploratory Data Analysis (EDA)**:  
   Conducted an in-depth analysis to understand the data distribution, identify patterns, and detect relationships between variables that influence turnover. This step provided key insights for feature selection and model development.

4. **Data Preparation**:  
   Prepared the data for machine learning models by encoding categorical variables, normalizing numerical features, and splitting the dataset into training and test sets.

5. **Predictive Modeling**:  
   Developed machine learning models to predict employee turnover risk, leveraging algorithms such as Logistic Regression, Random Forest, and Gradient Boosting. Hyperparameter tuning was performed to optimize model performance.

6. **Result Interpretation**:  
   Translated model outputs into actionable insights for business stakeholders, focusing on identifying high-risk employees and the key factors driving turnover.

7. **Dashboard Creation and Insights Generation**:  
   Designed and implemented an interactive dashboard to visualize findings. The dashboard allows users to explore employee data, analyze turnover trends, and identify actionable strategies to mitigate employee exits.

By following this structured process, the project delivers both predictive capabilities and meaningful insights to support strategic HR decision-making.

# 4. Top 5 Insights

1. **Employees with longer tenures are less likely to churn**  
   - Employees with more years of service tend to stay with the company, indicating that tenure is a strong factor in employee retention.  
   - ![Graph 1 - Tenure vs Turnover](https://github.com/user-attachments/assets/962de1df-6411-4330-836f-7d93f229f3fe)

2. **Salary and salary deviation from the department average are not significant predictors of turnover; however, higher earners are less likely to churn**  
   - While overall salary comparisons show little correlation with turnover, individuals in the higher salary brackets demonstrate greater stability.  
   - ![Graph 2 - Salary Range vs Turnover](https://github.com/user-attachments/assets/58204fc4-10c6-4be5-b472-69352b93c6ce)

3. **Employees in higher-ranking positions exhibit a higher average turnover rate**  
   - Senior roles might have elevated turnover due to increased stress, greater market demand for their expertise, or other job-related factors.  
   - ![Graph 3 - Job Hierarchy vs Turnover](https://github.com/user-attachments/assets/3e259cac-bd2d-4eba-b3f4-0cf4563cc7fd)

4. **Engagement surveys show no direct relationship with turnover causes; however, survey data may be biased**  
   - The lack of correlation suggests a possible limitation in how engagement is measured or reported.  
   - ![Graph 4 - Engagement vs Turnover](https://github.com/user-attachments/assets/ed304612-a485-4ca6-9320-18f1e693efa4)

5. **Satisfaction levels seem unrelated to turnover; however, survey results may also suffer from bias**  
   - The data shows no clear pattern linking satisfaction scores to turnover likelihood, which might indicate underlying inaccuracies in survey responses.  
   - ![Graph 5 - Satisfaction vs Turnover](https://github.com/user-attachments/assets/c71b5120-b996-49c5-9c8e-a4defb1d1426)

# 5. Machine Learning Models

Based on insights from the Exploratory Data Analysis (EDA) and feature selection using a Random Forest algorithm, the following features were identified as the most significant for predicting employee turnover:  
- `time_since_last_review`  
- `service_time`  
- `salary`  
- `absences`  
- `manager_workload`  
- `dept_id`  

Various algorithms were tested to evaluate their predictive performance, ranging from simpler models like **Logistic Regression** to more complex ones such as **Decision Tree**, **Random Forest**, and **Gradient Boosting**. 
Given the nature of the problem, **Recall** was chosen as the primary evaluation metric, as minimizing False Negatives is critical to ensuring that employees at high risk of leaving are correctly identified.

After testing, **Random Forest** was selected as the final model due to its superior performance in capturing potential churn cases and its balance between complexity and interpretability.


## 5.1 Model Performance

The Random Forest model initially achieved a **Recall of 0.88**, which was the highest among all models tested. After fine-tuning the hyperparameters, the Recall improved further to **0.895**. This performance highlights the model's 
capability to effectively identify employees at risk of turnover, reducing the likelihood of overlooking a potential churn case.

# 6. Business Results

The Random Forest algorithm was utilized not only to predict the likelihood of turnover but also to rank employees based on their risk levels. This ranking was enhanced by incorporating weights for characteristics most valuable to the company, 
such as performance metrics, ensuring that high-performing employees received higher prioritization for retention strategies.

From the analysis, **51 employees** were identified with a turnover probability above 70%. These employees were flagged as high-priority cases for intervention. By implementing targeted strategies to retain these individuals, 
the company could potentially avoid significant turnover-related costs.

### Cost Savings Calculation  
As established in the **Business Problem** section, the cost of turnover per employee is **R$20,000**. Preventing the turnover of these 51 employees would result in a total cost savings of:

**51 employees × R$20,000 = R$1,020,000**

This substantial cost reduction emphasizes the value of a data-driven approach to workforce management, enabling the company to proactively address turnover risks and allocate resources more effectively.

# 7. Visualization Dashboard

To provide a comprehensive overview of the company’s workforce and turnover metrics, **two dashboards** were created:

1. **Company Overview Dashboard**: This dashboard offers a high-level view of the company's employee distribution, key performance metrics, and overall trends in employee retention.
It helps HR and management teams understand the broader patterns in the workforce and make data-driven decisions.

3. **Turnover and Prevention Dashboard**: This dashboard focuses specifically on turnover metrics, highlighting employees at risk of leaving the company. It tracks turnover trends over time, identifies factors contributing to potential churn,
and allows the company to monitor the effectiveness of retention strategies in real time.

Below, you can find the visualizations for each of these dashboards:

### 1. Company Overview Dashboard  
![Company Overview Dashboard](https://github.com/user-attachments/assets/6a601112-e723-428d-b597-7e3f786d3c78)

### 2. Turnover and Prevention Dashboard  
![Turnover and Prevention Dashboard](https://github.com/user-attachments/assets/0fd7e461-f2e2-4d36-89b0-603d54209ddf)

# 8. Next Steps and Lessons Learned

## Next Steps to Improve

Looking ahead, several key improvements can be made to enhance the predictive power and usability of the turnover model:

- **Add External Data**: Integrating external datasets, such as market benchmarks and competitor data, could provide a better context for understanding employee behavior and turnover rates, helping refine predictions.
- **Implement an API for the Predictive Model**: Developing an API that allows easy access to the predictive model will enable real-time predictions for employee turnover risk, allowing HR teams to take timely actions.
- **Create Personalized Retention Plans**: Leveraging the insights gained from the model, customized retention strategies can be developed for employees at high risk of turnover. This would help in crafting more targeted and effective retention interventions.
- **Test and Improve**: Regular testing and updates to the model, incorporating new data and refining features, will help maintain its accuracy and effectiveness as employee dynamics evolve.

## Lessons Learned

Throughout this project, several valuable lessons were learned:

- **Understanding HR Domain**: It’s crucial to deeply understand the human resources domain to make meaningful interpretations of the data. Insights into the company’s culture, employee expectations, and HR policies play a significant role in effectively addressing turnover.
  
- **Challenges with Small Datasets**: Working with a relatively small dataset posed some challenges, especially in terms of training more complex models. However, the process provided insights into data limitations and the importance of feature selection and data preprocessing.
  
- **Dashboard Creation**: Designing dashboards that effectively communicate the findings to business stakeholders was a valuable skill. It highlighted the importance of clear visualizations and intuitive interfaces for decision-makers to act on the insights provided.

These experiences have not only strengthened the understanding of employee turnover dynamics but also provided a solid foundation for implementing and iterating on the predictive model in the future.






