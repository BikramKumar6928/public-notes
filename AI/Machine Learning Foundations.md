# What is Machine Learning

Machine learning is a subset of artificial intelligence that focuses on creating computer systems that can learn and predict outcomes from given examples without being explicitly programmed using data to automatically learn. 

Inference is a process of getting a prediction by giving a data point.

 > During the training process, the Training Data set is given to a learning algorithm as an input and it gives out the model(function) as an output.
> During the prediction process, the model is provided with its input and it provides the predicted output.


# Types of learning

## Supervised Machine Learning

In supervised machine learning, labelled data is used to train the model. Model learns the relation between features and labels.

Some of the popular applications of supervised machine learning are disease detection, weather forecasting, stock price prediction, spam detection, and credit scoring. For example, in disease detection, the patient data is input to a machine learning model, and machine learning model predicts if a patient is suffering from a disease or not.

> The point is that if a label can be found by using contemporary measures corresponding to a data, then supervised learning can be used.
## Unsupervised Machine Learning
Unsupervised learning is generally used to understand relationships within a data set. Labels are not used or are not available.

For unsupervised machine learning, some of the most common real time applications are to detect fraudulent transactions, customer segmentation, outlier detection, and targeted marketing campaigns. So for example, given the transaction data, we can look for patterns that lead to fraudulent transactions.

> As said above, you cannot predict which transactions are fraudulent using contemporary measures. There will always be transactions which were fraudulent but were not reported. So using unsupervised data is better here.

## Reinforcement learning

Reinforcement learning uses algorithms that learn from outcomes (like interacting with an environment) to make decisions or choices.

Most popular among reinforcement learning applications are automated robots, autonomous driving cars, and playing games.

> Where we can interact with some environment and get positive and negative feedback, reinforcement learning can be used.


# Types of Supervised Learning

## Regression
It is used in case of continuous output is required. A numeric output is given. 

Example -> House Price Predictor
### Linear Regression

This is done by fitting the data into a line. The slope and bias (y-intercept) is iteratively adjusted to perform the fitting.

`Loss` is a number indicating how far the predicted value is from the actual value.
We have to minimise the loss.

One of the ways to calculate `loss` is to take a difference between predicted and actual value, and square it.

> Squared difference for getting the loss

## Classification
It is used in case of categorical output is required. A label/category is given as output.

Classification is a supervised machine learning technique used to categorise or assign data points into predefined classes or categories, based on their features or attributes. Classifier is trained on a labelled data set.

Example -> Cat/Dog identifier

It has the following subcategories:

- Binary -> If the output is true or false. Example-> Spam Detector
- Multi-class -> If the output has multiple categories. Example -> Sentiment Analysis. This is used to find if a given text is positive, negative or neutral sentiment.


### Logistic Regression
Logistic regression is an algorithm for Binary classification.

Logistic regression uses an S-shaped curve called the Sigmoid function to fit the data. The Sigmoid function takes any real valued number and squashes it into a range between 0 and 1.

Output from the Sigmoid function is to be compared with a threshold value of, say, 0.5. If output is more than 0.5, it would be classified as a true. And if less than 0.5, it will be classified as a false.


# Python Libraries

```python
from sklearn.linear_model import LogisticRegression # module used to train a model using Logistic Regression Approach. Takes the inputs and labels for training and takes inputs and predicts the trained value.
from sklearn.model_selection import train_test_split # divides data into training and testing set
from sklearn.preprocessing import StandardScaler # Standardizes data with mean of 0 and standard deviation of 1
from sklearn.metrics import accuracy_score # It calculates the ratio of correctly predicted instances to the total number of instances in the data set.
```

