# ❤️ Topic: Customer Shopping Trends

## Overview:
This repo contains the project files for the SC1015 mini-project from FCSF Group 6. \
In the rapidly evolving retail landscape, businesses face significant challenges in meeting the diverse preferences of consumers. Additionally, without accurate predictions of product ratings, sellers may miss critical insights into consumer feedback that could drive improvements. \
We use data science and machine learning to enhance the shopping experience by personalising product recommendations for shoppers and predicting product ratings for sellers. \
Listed here are the ipynb files used, which should be view in numerical order.

1. [Data Extraction and Visualisation](./Data-Extraction-and-Analysis.ipynb)
2. [Linear Regression](./Linear-Regression.ipynb)
3. [Random Forest](./Random-Forest.ipynb)
4. [XGBoost](./XGboost.ipynb)

## Dataset:
The dataset that we have chosen is taken from [Kaggle](https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data) and contains data of customer shopping trends.

## Methodology:
### [Data Extraction and Visualisation](./Data-Extraction-and-Analysis.ipynb)

The dataset includes a combination of numerical values and categorical values.

- **Data Cleaning**: 
    - Handle invalid and NaN values
    - Handle duplicate values
    - Check the data type consistency
    - Check the label consistency and correctness

- **Data Visualisation**:
    - Do uni-variate and multivariate analysis on numerical data.
    - Use bar chart and heatmap to visualise Item Purchased against different categorical data. We get some useful information like seasonal purchasing trend and regional purchasing trend.
    - Use boxplots to visualise the Review Rate against different categorical data.


### [Linear Regression](./Linear-Regression.ipynb)
The Linear Regression model, used as our baseline, successfully enabled us to predict customer review ratings based on their purchase data. Despite some limitations, including a relatively low explained variance of around 0.046 for the training dataset and -0.059 for the test dataset, and a high Mean Square Error of approximately 0.48 for the training dataset and 0.56 for the test dataset, the model still provides a foundation for predicting review ratings. The goodness of fit was -0.056, indicating room for improvement in predictive accuracy. 
To validate the model's capability, we tested it on 5 customer predictions, with the majority having over 10% prediction error. While the model has its shortcomings, it offers a starting point for understanding the relationship between customer purchases and review ratings. Given these initial insights, further refinement with a more complex model is needed to enhance prediction accuracy.

### [Random Forest](./Random-Forest.ipynb)
The dataset was prepared with one-hot encoding to transform categorical data into boolean type. 
The Random Forest Classifier achieved a high accuracy rate of 98.42%, and K-Fold cross-validation further validated its performance with a mean accuracy of 0.504 and an improved goodness of fit of 0.057. Feature importance analysis identified the location as the most influential factor on customer review rates, followed by item colour and type. 
For the Random Forest Regression, data was split into an 8:2 train-test ratio, and GridSearchCV was used for parameter tuning, resulting in significantly improved prediction accuracy where all 5 tested customer predictions had a percentage error under 10%.

### [XGBoost](./XGboost.ipynb)
In our final approach, we employed the XGBoost model for product recommendations to customers. Data preparation mirrored that of linear regression and random forest, using one-hot encoding for categorical data. 
While the train dataset accuracy was decent at 0.67, the test accuracy was notably lower at 0.14. 
However, given the diverse range of products, this result is considered acceptable since precise predictions on customer purchases are inherently challenging. 
Interestingly, while the Random Forest model indicated that 'Category' was the least important factor in predicting review rates, XGBoost highlighted its significance. This is logical, as customer satisfaction is primarily influenced by whether the recommended item aligns with their desired category. In a practical scenario, entering customer information yields a product recommendation—in this case, a T-shirt was suggested for the customer.

## Results:
This table presents performance metrics for both the Linear Regression and Random Forest models.

| Model                    | Mean Squared Error (MSE)   | Accuracy (Goodness of fit) |
|--------------------------|----------------------------|----------------------------|
| Linear Regression        | 0.57                       | -0.05665                   |
| Random Forest            | 0.55                       |  0.05672                   |

## Conclusion:
In conclusion, we have found that for predicting review ratings location is the most important factor and for recommending an item to a customer, category is the most important factor.

When comparing Random Forest to Linear Regression for the prediction of review rating of items, Random Forest is a better-predicting model as it has higher accuracy and lower error percentage. 
The XGBoost model is also a solid model for recommending to a new customer an item, as its accuracy is decently high as well. 

## Contributors
1. @AlasamAkkit
2. @Tyingjie
3. @mendax1234

## References
- https://www.analyticsvidhya.com/blog/2021/05/all-you-need-to-know-about-your-first-machine-learning-model-linear-regression/

- https://xgboost.readthedocs.io/en/stable/

- https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html

