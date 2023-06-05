# GridSearchCV
GridSearchCV in scikit-learn is a technique used for hyperparameter tuning, which involves systematically searching for the best combination of hyperparameters for a machine learning model. It automates the process of finding the optimal hyperparameters by exhaustively searching through a predefined grid of parameter values and evaluating the model's performance for each combination.  
**Hyperparameter tuning** is an important step in machine learning to find the best combination of hyperparameters for a given model. Hyperparameters are parameters that are set before training the model and cannot be learned from the data. They control the behavior of the learning algorithm and can significantly impact the model's performance.

Here's how GridSearchCV works in scikit-learn:

1)Defining the Parameter Grid: First, you define a dictionary or a parameter grid that specifies the hyperparameters and the corresponding values to be searched. Each key in the dictionary represents a hyperparameter, and the associated value is a list of possible values to try.

2)Creating the Estimator: Next, you create an instance of the estimator (the machine learning model) that you want to tune. This could be any estimator from scikit-learn, such as a classifier or a regressor.

3)Instantiating GridSearchCV: You create an instance of the GridSearchCV class, passing the estimator, the parameter grid, and other optional parameters such as cross-validation settings and scoring metric.

4)Performing Grid Search: You call the fit method of the GridSearchCV object, which performs an exhaustive search over the parameter grid. For each combination of hyperparameters, it trains the estimator and evaluates its performance using cross-validation.

5)Identifying the Best Parameters: After the grid search is complete, you can access the best combination of hyperparameters found by the GridSearchCV using the best_params_ attribute.

6)Accessing the Best Estimator: You can also access the best estimator (trained on the full training data with the best hyperparameters) using the best_estimator_ attribute. This allows you to use the best model for further analysis or making predictions.

Here's an example of using GridSearchCV for hyperparameter tuning with a Support Vector Machine (SVM) classifier:
```py 
from sklearn.model_selection import GridSearchCV
from sklearn.svm import SVC
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split

# Load the Iris dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Define the parameter grid for the SVM classifier
param_grid = {'C': [0.1, 1, 10], 'gamma': [0.1, 1, 10], 'kernel': ['linear', 'rbf']}

# Create an instance of the SVM classifier
svm = SVC()

# Create GridSearchCV object
grid_search = GridSearchCV(svm, param_grid, cv=5)

# Perform grid search
grid_search.fit(X_train, y_train)

# Access the best hyperparameters
best_params = grid_search.best_params_
print("Best Hyperparameters:", best_params)

# Access the best estimator
best_estimator = grid_search.best_estimator_
print("Best Estimator:", best_estimator)

# Evaluate the model on the testing data
accuracy = best_estimator.score(X_test, y_test)
print("Accuracy:", accuracy)

```

