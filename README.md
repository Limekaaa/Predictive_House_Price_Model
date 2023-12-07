## Team members

Alix Lanotte Moro - Léonard de Vinci Graduate School of Engineering - alixlanottemoro@gmail.com

Jeremie Formey de Saint Louvent - Léonard de Vinci Graduate School of Engineering - jeremie.formey_de_saint_louvent@edu.devinci.fr

Victoria Gauthier - Léonard de Vinci Graduate School of Engineering - victoria.gauthier@edu.devinci.fr

Maxime Hanus - Léonard de Vinci Graduate School of Engineering - maximehns@hanyang.ac.kr 

## 1 Introduction 
### Motivation

Our first motivation is that some of us have learned about machine learning theory, and now, we are enthusiastic about witnessing its application in the real world. This project serves as a practical link between theoretical understanding and real-world implementation. Therefore, we are impatient to apply the coding skills acquired in R or Python during our academic pursuits. This project provides an opportunity to translate theoretical coding knowledge into practical use, specifically in predicting house prices. Moreover, the prominence of data science in engineering, this project represents a collective effort to explore deeper into this field. It positions us to be well-prepared for roles where data plays a significant role.

### What we want to see at the end ?

The ultimate objective is to witness the practical application of our collective knowledge in addressing a real-world problem : predicting house prices. Successfully making a difference in this realm signifies the tangible impact we strive for. The project serves as a practical showcase of our understanding of machine learning theory. We anticipate a tangible manifestation of how theoretical concepts translate into real-world applications.

## 2 Description of the dataset : Predictive House Price Model

The "Predictive House Price Model" is a project aimed at developing an advanced machine learning model that predicts the sale prices of houses based on various input parameters.
This dataset, part of a Kaggle competition, targets individuals with some experience in R or Python and basic machine learning knowledge. Ideal for data science students who completed an online machine learning course, the competition focuses on predicting the final price of homes in Ames, Iowa, using 79 explanatory variables covering nearly every aspect of residential properties. The dataset, compiled by Dean De Cock for data science education, serves as a modernized version of the well-known Boston Housing dataset. Participants are tasked with employing creative feature engineering and advanced regression techniques such as random forest and gradient boosting to predict home prices.
This is our proposition to solve the problem of the kaggle competition **House Prices - Advanced Regression Techniques** in the best way we can. To do this we will use several techniques of Machine Learning and will be written in Python.

## 3 Methodology
### Explaining your choice of algorithms and features or code

The first step was pre-processing: we removed the rows with no target (SalePrice) in the training dataset only, as the test datasets obviously have no target values here. We then found that we had the same number of rows, so there were no missing values in the target column. We combined the datasets to clean, pre-process and explore them.
Taking a look at the presence of null values in columns first, before looking at the nulls per rows. Some columns here have way too many null values, which means that the data is incomplete for these. Obviously we are goign to keep the 'SalePrice' column (and instead remove the rows for which the price is missing...) for the others, such as Fence or MiscFeature, we are going to remove the column itself when the number of missing values exceed 10% of the total number of rows. Taking away rows for which all values are null. Then the separation for the initial datasets following the value in the dataset_type column, created in order to keep track of each row's appartenance before the combination of the two original datasets, train_dataset and test_dataset.
The second one was to train the two models random forest predictions and XGBoost predictions. We can afford to use all of the columns, as none are extremely correlated. We can interestingly see that there are certain columns that strongly influence the price of the house (SalePrice), for example the elements regarding the Garage, or the presence of a second floor. First, to use the Random Forest algorithm, we import all the libraries needed, and also the libraries used to make some graphs. We split the train dataset into two dataset, one for the training and the other to test the accuracy of the model before using it for the predictions
We test it with several values for the n_estimators in order to use a good one. We see that the best n_estimator is 500, so we will keep it for the predictions.Then we trained the XGBoost Predictions. We can see the best models are the third and fourth. Let's tune parameters to get even better model. Our best model is the second one so we continue with this one. We can see this model is precise around house prices between 100k and 200k. Out of this thresold we can see the error is bigger.


