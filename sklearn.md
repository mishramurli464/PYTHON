# sklearn
**scikit-learn** (or sklearn) is a popular Python library for machine learning. It provides a wide range of tools and algorithms for tasks such as classification, regression, clustering, and 
dimensionality reduction. scikit-learn is built on top of other popular scientific computing libraries like NumPy, SciPy, and Matplotlib, making it a powerful and convenient choice for 
machine learning tasks.  
steps involved in using scikit-learn to build a machine learning model:

a)Importing Libraries: Begin by importing the necessary libraries, including scikit-learn and other relevant libraries like NumPy and Pandas.

b)Loading and Preparing Data: Load your dataset into memory, and perform any necessary data preprocessing steps such as handling missing values, feature scaling, encoding categorical variables,
and splitting the data into training and testing sets.

c)Choosing an Estimator: Select an appropriate estimator (machine learning algorithm) based on the nature of your task, whether it is classification, regression, clustering, etc.

d)Creating an Instance of the Estimator: Instantiate an object of the chosen estimator by specifying any desired parameters.

e)Training the Model: Use the fit method of the estimator to train the model on the training data. This involves providing the features (X_train) and the corresponding target values (y_train).

f)Making Predictions: Once the model is trained, use the predict method to make predictions on new, unseen data. You can use the trained model to predict the target variable for the testing dataset
(X_test) or any other new data.

g)Model Evaluation: Evaluate the performance of the model by comparing the predicted values with the actual values. Use appropriate evaluation metrics such as accuracy, precision, recall, mean squared
error, etc., depending on the specific task.

h)Hyperparameter Tuning: Adjust the hyperparameters of the model to improve its performance. Use techniques like grid search or random search to find the optimal combination of hyperparameters.

i)Model Persistence: If you are satisfied with the model's performance, you can save the trained model to disk for future use. This can be done using scikit-learn's joblib or pickle modules.

j)Deployment and Inference: Once the model is trained and saved, you can deploy it to a production environment or use it for making predictions on new, real-time data. 


## preprocessing
Preprocessing is an essential step in machine learning that involves transforming raw data into a suitable format for training machine learning models. scikit-learn provides a variety of 
preprocessing techniques and tools to help prepare data for analysis. Handling Missing Data, Feature Scaling, Categorical Variable Encoding, Dimensionality Reduction, Feature Extraction, Data 
Normalization &  Data Splitting  are some commonly used preprocessing techniques in scikit-learn

## metrices
In scikit-learn, metrics are functions or methods used to evaluate the performance of machine learning models. These metrics provide a quantitative measure of how well the model is performing on a
given task, such as classification or regression. scikit-learn provides a wide range of metrics that can be used to assess different aspects of model performance. Here are some commonly used metrics 
in scikit-learn:

1) Classification Metrics:

Accuracy: Measures the fraction of correctly classified samples.
Precision: Quantifies the fraction of true positive predictions out of all positive predictions.
Recall: Measures the fraction of true positive predictions out of all actual positive samples.
F1 Score: Harmonic mean of precision and recall, providing a balanced measure of the two.
Confusion Matrix: Provides a tabular representation of predicted labels versus true labels, enabling analysis of true positives, true negatives, false positives, and false negatives.

2)Regression Metrics:

Mean Absolute Error (MAE): Measures the average absolute difference between predicted and true values.
Mean Squared Error (MSE): Calculates the average squared difference between predicted and true values.
Root Mean Squared Error (RMSE): The square root of MSE, providing a more interpretable metric.
R2 Score (Coefficient of Determination): Measures the proportion of the variance in the dependent variable explained by the independent variables.

3)Clustering Metrics:

Adjusted Rand Index (ARI): Compares the similarity between true and predicted cluster assignments, considering all pairs of samples.
Silhouette Coefficient: Quantifies how similar an object is to its own cluster compared to other clusters.

4)Ranking Metrics:

Mean Average Precision (MAP): Measures the average precision across different levels of retrieved items in a ranking scenario.

5)Multi-label Classification Metrics:

Hamming Loss: Measures the fraction of misclassified labels.
Subset Accuracy: Measures the exact match ratio for the entire set of labels.  

## meta estimators in sklearn
estimators are objects that learn from data and make predictions. They form the core components of machine learning models in scikit-learn. Estimators implement the fit method to learn from data 
and the predict method to make predictions on new data. **meta-estimators** are high-level estimators that wrap around other estimators, allowing you to modify the behavior of the base estimators
or combine multiple estimators into a single model. Meta-estimators provide additional functionality and flexibility to enhance the performance and capabilities of the underlying base estimators.
Here are some commonly used meta-estimators in scikit-learn:
VotingClassifier: This meta-estimator combines multiple individual classifiers (e.g., logistic regression, decision tree, support vector machine) and aggregates their predictions using majority 
voting or weighted voting. It can be useful for ensemble learning and model combination.

VotingRegressor: Similar to VotingClassifier, this meta-estimator combines multiple individual regressors and aggregates their predictions using averaging or weighted averaging.

StackingClassifier: StackingClassifier combines multiple base classifiers with a meta-classifier. The base classifiers make predictions, and the meta-classifier learns to combine those predictions
to make the final prediction. StackingClassifier can be used for stacking ensemble methods.

StackingRegressor: Similar to StackingClassifier, this meta-estimator combines multiple base regressors with a meta-regressor for making the final prediction.

BaggingClassifier: BaggingClassifier fits multiple instances of a base classifier on different bootstrap samples of the training data. It then aggregates their predictions through majority voting or
averaging to make the final prediction. BaggingClassifier can improve the stability and generalization of the base classifier.

BaggingRegressor: Similar to BaggingClassifier, this meta-estimator applies bagging to multiple instances of a base regressor and aggregates their predictions using averaging.

AdaBoostClassifier: AdaBoostClassifier trains a sequence of weak classifiers iteratively, with each subsequent classifier focusing more on the samples that were incorrectly predicted by previous classifiers.
It combines the predictions of weak classifiers to make the final prediction.

AdaBoostRegressor: Similar to AdaBoostClassifier, this meta-estimator applies AdaBoost to a sequence of weak regressors.
