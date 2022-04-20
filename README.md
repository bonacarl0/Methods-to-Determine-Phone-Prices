# Phone Prices Classification
Data is taken from: https://www.kaggle.com/iabhishekofficial/mobile-price-classification
# Define Problem
1. There are a lot of people try to bring new innovations to mobile phone in this of ever-transforming technology world, but there are a lot of a strong existed mobile phone company, along with their various-ranging prices. The author of this project aims to give a guidance or instruction for the upcoming innovators of mobile phone, of what they can offer in their products, especially letting them know what are the features that really take part in determining the price of the phone.
2. The output of this project is the launching of the most important feature to the idea of grouping the mobile phone prices.
Machine learning task that is going to be used for this project is supervised learning, with models such as: Decision Tree Classifier, K Nearest Neighbors, and Logistic Regression.
3. Evaluation metrics for the models are R Squared score.
4. The risk that is going to be encountered after the release of this project is although the features that has been resulted have a strong role to determine mobile phone range price, there is still going to be an external factor that can clout the market's interest for buying mobile phones. Consider a trend of a colored phone in early 2000s can really attract mass buyers to buy the product, although the functionality of the product is not really the priority. Future mobile phone innovators discretion may be advised.

# Data Preparation
The steps comprises of importing the dataset, Exploratory Data Analysis (EDA), choosing relevant features to be used, scaling numerical features

# Modeling
Multiple classification models were used to classify the model: Logistic Regression, Decision Tree Classifier, and KNeighborsClassifier. From the models used, considering the most optimum evaluation metric scores that do not overfit, Logistic Regression model was chosen to be the model for the classification, as so hyperparameter tuning was done to the model, the parameters are shown below;
```
from sklearn.model_selection import GridSearchCV
param_grid = {
    'log_reg__C' : [1,0.1,0.01],
    'log_reg__fit_intercept' : [True, False]
}

grid_search = GridSearchCV(pipeline_log_reg, param_grid, cv=5, scoring=precision_scorer)
```

# Result
![download](https://user-images.githubusercontent.com/87014423/164160725-8c878b33-e654-428e-8412-62eb5b10463f.png)
It is seen that Ratio Ram Memory feature is the most determining factor in classification for the mobile price range, we also can see that there is also not too many differences for the 0, and 1 class (low cost, and medium cost) with the 2, and 3 class (high cost, and very high cost). For further analyses or project, we also can divide the price range class into two classes only to simplify user in determining their mobile phone price range.

# Deployment Model
Datas from features were synthesised to make a simulation of deploying the model to the field.
![Screenshot 2022-02-12 174434](https://user-images.githubusercontent.com/87014423/153708157-7848d712-f80a-4d26-b38d-cb433c9ebd3d.jpg)
The best model then is used to predict the best model of the synthesised datas:
![Screenshot 2022-02-12 174708](https://user-images.githubusercontent.com/87014423/153708264-626aabfa-243b-4bc2-b348-0f776c52f8b6.jpg)
