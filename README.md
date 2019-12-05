# Telecom-Churn

Business Overview

In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition. For many incumbent operators, retaining high profitable customers is the number one business goal.

To reduce customer churn, telecom companies need to predict which customers are at high risk of churn.
Objective

In this project, we will

    analyze customer-level data of a leading telecom firm,
    build predictive models to identify customers at high risk of churn and
    identify the main indicators of churn.

Churn Definition

This project is based on Indian and Southeast Asian market and fillowing Usage-based Churn definition will be used:

Usage-based churn:Customers who have not done any usage, either incoming or outgoing - in terms of calls, internet etc. over a period of time.
High Value Churn

In the Indian and the southeast Asian market, approximately 80% of revenue comes from the top 20% customers (called high-value customers). Thus, if we can reduce churn of the high-value customers, we will be able to reduce significant revenue leakage.
Data and Business Objective

dataset: The dataset contains customer-level information for a span of four consecutive months - June, July, August and September. The months are encoded as 6, 7, 8 and 9, respectively.

business objective: is to predict the churn in the last (i.e. the ninth) month using the data (features) from the first three months.
Understanding Customer Behaviour during Churn

Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle :

    The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.

    The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.)

    The ‘churn’ phase: In this phase, the customer is said to have churned. We define churn based on this phase.

In this project, since we are working over a four-month window:

    the first two months (6th and 7th month data) are the ‘good’ phase,
    the third month (8th month) is the ‘action’ phase,
    while the fourth month (9th month) is the ‘churn’ phase.

Approach and final solution

The following approach was followed for churn modeling:

    Data load, cleaning and Exploratory Data Analysis was done.
    From above steps useful patterns were identified, in particular a significant drop in many features was observed during action phase.
    Handling of NA values and outliers was done on a feature by feature basis.
    Relationships among different features were also identified during EDA phase, and feature for which there were component features present in the data set were dropped.
    Feature engineering was done, in particular the following broad steps were taken:
        New features were created for good phase by taking the average of 6th and 7th month values.
        New features were derived from date related values.
        New features were derived in action phase by taking the difference between good phase and 8th month corresponding features.
    Feature standardization was done.
    As the data set is highly imbalanced towards the 'Non-churn' majority class, imbalanced data set handling was done, specifically the following two techniques were followed.
        SMOTE: synthetic sample generation for minority class.
        Majority class under sampling.
    From above majority class under sampling gave better results and hence was used for final model building. Data was divided into training and test set.
    Basic model was created using Logistic Regression.
    As churn prediction is primary motive sensitivity and f1 score were looked into to be maximized.
    Feature reduction was done using PCA (the reduced feature set contained ~ 35 feature).
    Baseline model was created.
    Multiple boosting models were tried namely - Ada Boost,Gradient Boosting and XgBoost.
    An ensemble model using majority vote strategy was also created using Logistic Regression, Decision trees, Random Forest and Linear SVM.
    The best prediction model was obtained using XgBoost were a sensitivity of approx. 90% a precision of 33% and f1 score of 48% was obtained.
    For understanding factors for churn a logistic regression model was build and features influencing churn were obtained using LASSO and feature elimination using high p-value and VIF for multicollinearity.
    Finally recommendation and strategies were suggested for reducing churn.


