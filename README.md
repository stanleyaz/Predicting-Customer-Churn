# Predicting-Customer-Churn-For-Brass

## Author: Stanley Azuakola

---

# Problem Statement
[Brass Business Bank (Brass)](https://www.trybrass.com/about/), a B2B company - founded in Lagos, Nigeria [less than three years ago](https://brassbanking.medium.com/introducing-brass-banking-nigerias-local-businesses-143c0ccf2bb8) - has asked me to predict customer churn for their business using a subset of customers and their transactions. Churn refers to when customers stop using a product. Brass offers commercial-grade current accounts, financial products, education, financing and partnership to support its clients which are all businesses. Churn is a big problem for this business - as it is with many others - because churning customers means loss of revenues and potential profits, and would then lead to expending more money to find new customers which is a more expensive undertaking than retaining existing customers. Churn can also be harmful to the brand if churned customers who leave because of bad experience(s) spread negative word of mouth.

The requirements for this task are as follows:
1. To train a classifier that can predict customer churn for Brass.
2. To define churn for Brass - using the data provided by the company. In the data provided, Brass did not label any customer as `churned` or `not churned`. It is my responsibility to come up with a definition of churn to be used for my analysis and modeling. 
3. To engineer features that will be used in predicting churn. Brass was unable to share much demographic data due to security concerns about sharing customer information with me as a non-staff who is not physically on site. 

---

# Metrics for Evaluation

Since the classes in this project are unbalanced, we cannot rely exclusively on accuracy as the metric of choice for evaluation. Brass does not tell me what metrics to use in my evaluation, but I chose the below five metrics.

1. Accuracy score
2. Balanced accuracy score
3. Recall/Sensitivity
4. Geometric mean
5. Fbeta score 

Explanations for my choice of these metrics are provided in my [first notebook](notebooks/01_introduction.ipynb). 

---

# Contents

### Jupyter notebooks
1. [Introduction and Data cleaning](notebooks/01_introduction.ipynb)
2. [Exploratory Data Analysis](./code/02_extract_images_and_data.ipynb) from downloaded files, and cleaning them
3. [Feature Engineering](./code/03_EDA.ipynb) of non-image data
4. [Preprocessing and Modelling](./code/04_Baseline_model.ipynb) that does not use satellite imagery
5. [Analysis and Conclusions](./code/05_nn_modeling.ipynb)