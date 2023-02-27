# Predicting-Customer-Churn-For-Brass

## Author: Stanley Azuakola

---

# Problem Statement
[Brass Business Bank (Brass)](https://www.trybrass.com/about/), a B2B company - founded in Lagos, Nigeria [less than three years ago](https://brassbanking.medium.com/introducing-brass-banking-nigerias-local-businesses-143c0ccf2bb8) - has asked me to predict customer churn for their business using a subset of customers and their transactions. Churn refers to when customers stop using a product. Brass offers commercial-grade current accounts, financial products, education, financing and partnership to support its clients which are all businesses. Churn is a big problem for this business - as it is with many others - because churning customers means loss of revenues and potential profits, and would then lead to expending more money to find new customers which is a more expensive undertaking than retaining existing customers. Churn can also be harmful to the brand if churned customers who leave because of bad experience(s) spread negative word of mouth.

The requirements for this task are as follows:
1. To train a classifier that can predict customer churn for Brass.
2. To define churn for Brass - using the data available. The data provided by Brass did not label any customer as `churned` or `not churned`. It is my responsibility to come up with a definition of churn to be used for my analysis and modeling. 
3. To engineer features that will be used in predicting churn. Brass was unable to share much demographic data due to security concerns about sharing customer information with me as a non-staff who is not physically on site. 

# Metrics for Evaluation

With that in mind, it would not make much sense to rely exclusively on accuracy as the metric of choice for the evaluation of our model.

For this problem, we would consider five evaluation metrics:
- **Accuracy score**: Inclusion of accuracy score here is mainly just because it is customary practice. But for an inbalanced dataset, the accuracy score can be misleading and practically useless. 
- **Balanced accuracy score**: Balanced accuracy takes the average of sensitivity and specificity. In terms of accuracy scores, this is preferable to the traditional accuracy score as it measures the average accuracy obtained from the majority and minority classes. If the model performs just as well for both churn and not churn, then balanced accuracy would be same as accuracy score. However if model just taking advantage of the positive class(not churn), then balanced accuracy drops.
- **Recall/Sensitivity**: This is an important metric for us because recall minimizes the false negatives, which is absolutely what we want here. Brass can afford false positives (i.e. when model says a customer is churning when the customer isn't.) Worst case there is to make oureaches to such a customer and there's no harm in that. However if the model says a customer is not churning when the customer is in fact chrning, then Brass would lose such a customer - which is the opposite of what we want. 
- **Geometric mean**: The geometric mean measures the balance between the classification performances in both the positive(churn) and negative(not churn) classes. It is the square root of (sensitivity * specificity), and would be low if the model does great at classifying the negative classes but performs poorly with the positive classes.
- **Fbeta score**: The Fbeta score is calculated using precision and recall. It is related to the F1-score which is the harmonic mean between precision and recall. However, whereas the F1-score gives equal weighting to both precision and recall, the Fbeta score has a beta parameter that can be adjusted to give a bigger weight to one or the other. In our case we would weigh the recall more by giving the beta a value of 1.5. 


# Contents

### Jupyter notebooks
1. [Data collection](./code/01_download_tfrecords.ipynb)
2. [Extracting images and other data](./code/02_extract_images_and_data.ipynb) from downloaded files, and cleaning them
3. [Exploratory data analysis](./code/03_EDA.ipynb) of non-image data
4. [Baseline modeling](./code/04_Baseline_model.ipynb) that does not use satellite imagery
5. [Neural network modeling and training](./code/05_nn_modeling.ipynb)
6. [Final modeling](./code/06_final_modeling.ipynb) and analysis of our production model's performance

If using our pre-downloaded and pre-exported data, you can skip notebooks 1 and 2.