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

Types of Supervised Learning:
### Regression
It is used in case of continuous output is required. A numeric output is given. 

Example -> House Price Predictor
#### Linear Regression

This is done by fitting the data into a line. The slope and bias (y-intercept) is iteratively adjusted to perform the fitting.

`Loss` is a number indicating how far the predicted value is from the actual value.
We have to minimise the loss.

One of the ways to calculate `loss` is to take a difference between predicted and actual value, and square it.

> Squared difference for getting the loss

### Classification
It is used in case of categorical output is required. A label/category is given as output.

Classification is a supervised machine learning technique used to categorise or assign data points into predefined classes or categories, based on their features or attributes. Classifier is trained on a labelled data set.

Example -> Cat/Dog identifier

It has the following subcategories:

- Binary -> If the output is true or false. Example-> Spam Detector
- Multi-class -> If the output has multiple categories. Example -> Sentiment Analysis. This is used to find if a given text is positive, negative or neutral sentiment.


#### Logistic Regression
Logistic regression is an algorithm for Binary classification.

Logistic regression uses an S-shaped curve called the Sigmoid function to fit the data. The Sigmoid function takes any real valued number and squashes it into a range between 0 and 1.

Output from the Sigmoid function is to be compared with a threshold value of, say, 0.5. If output is more than 0.5, it would be classified as a true. And if less than 0.5, it will be classified as a false.

### Python Libraries

```python
from sklearn.linear_model import LogisticRegression # module used to train a model using Logistic Regression Approach. Takes the inputs and labels for training and takes inputs and predicts the trained value.
from sklearn.model_selection import train_test_split # divides data into training and testing set
from sklearn.preprocessing import StandardScaler # Standardizes data with mean of 0 and standard deviation of 1
from sklearn.metrics import accuracy_score # It calculates the ratio of correctly predicted instances to the total number of instances in the data set.
```

train_test_split takes an input `random_state` which is used to set the seed for randomly taking values from the training data. The state setting is required for repeatability.

For StandardScaler, you fit_transform the training data and transform the test data
This is done so that the training data would have a Standard Deviation of 1 and Mean 0 and the test data must be changed in a way that the test value makes sense after the transform.

The test data is also not taken into account while fitting as you would not always know the test data that can come in future.


## Unsupervised Machine Learning

Unsupervised learning is generally used to understand relationships within a data set. Labels are not used or are not available.

Unsupervised learning is used when there are no labelled outputs in the training data.

In unsupervised machine learning, the patterns in the data are explored explicitly without being told what to look for.

For unsupervised machine learning, some of the most common real time applications are to detect fraudulent transactions, customer segmentation, outlier detection, and targeted marketing campaigns. So for example, given the transaction data, we can look for patterns that lead to fraudulent transactions.

> As said above, you cannot predict which transactions are fraudulent using contemporary measures. There will always be transactions which were fraudulent but were not reported. So using unsupervised data is better here.

Use Cases:

- Market Segmentation -> For example, customers with a particular age group who buy protein diet products can be shown in advertisement of sports-related products.
- Outlier Analysis -> For example, credit card purchase data is provided for clustering. Fraudulent transactions can be detected by a bank by using outliers. In some transaction, amounts are too high or recurring, it signifies an outlier.
- Recommendation System -> For example, users' movie viewing history is provided as input to a clustering algorithm. It clusters users based on the type or rating of movies they have watched. It can then recommend similar movies to the users.
### Clustering

Clustering is a method of grouping data items based on similarities. Within a cluster, the data items are more similar than the items outside the cluster.

If some data items do not fall within any cluster, these data items are deemed as outlier points.

### Similarity

Similarity is how close two data points are to each other and is a value between zero and one. Similarity between objects decide which cluster they will fall into, and hence important for clustering.

### Workflow for Unsupervised Learning

#### Prepare the data

While preparing the data, the basic preprocessing steps, like removing missing values, normalizing the data, and feature scaling are performed.

#### Create similarity metrics

The choice on which similarity metrics to use depends on the nature of the data and the specific clustering algorithm being used. Some common similarity metrics, which are frequently used, are:

- Euclidean distance metric
- Manhattan distance metric
- cosine similarity metric
- Jaccard similarity metric.

#### Run the clustering algorithm.

Clustering algorithms use similarity matrix to cluster the data. The different types of clustering algorithms are:
- partition-based
- hierarchical-based
- density-based
- distribution-based.

#### Interpret the results and adjust your clustering

Checking the quality of your clustering output is iterative and exploratory. Because there is no labelled output, clustering lacks the ground truth that can verify the output.

Verify the results against expectations at the cluster level and the example level. Improving the result requires iteratively experimenting with the previous steps to see how they affect the clustering.

## Reinforcement learning

Reinforcement learning uses algorithms that learn from outcomes (like interacting with an environment and receiving feedback in the form of rewards or penalties) to make decisions or choices. No labelled (or unlabelled data) is required for reinforcement learning.

Most popular among reinforcement learning applications are automated robots, autonomous driving cars, and playing games.

> Where we can interact with some environment and get positive and negative feedback, reinforcement learning can be used.

The goal of reinforcement learning algorithm is to find the policy that will yield a lot of rewards for the agent if the agent follows that policy, referred to as the optimal policy.

Example Algorithms:

- Q learning
- Deep Q learning
### Terminology

For more clarity, the example of a self-driving car is taken for defining the terms

#### Agent

Agent is a learner or decision maker that interacts with the environment, takes actions, and learns from the feedback received. In this example, car and its intelligence to steer on the road is called as an agent.

#### Environment

Environment is the external system with which the agent interacts. In this example, environment is the road and its surroundings with which the car interacts.

#### State
State is a representation of the current situation or configuration of the environment at a particular time. It contains the necessary information for the agent to make decisions.It is the world or context in which the agent operates and receives feedback for its actions. In this example, what we see through a camera in front of a car at a moment is a state.

#### Action

Actions are a set of possible moves or decisions that the agent can take in a given state. Actions have an impact on the environment and influence future states. In this example, the actions are to drive left, or right, or keep straight.

#### Policy

Policy is a strategy or mapping that the agent uses to decide which action to take in a given state. It defines the agent's behavior and determines how it selects actions. In this example, after driving through the road many times, the car learns what action to take when it views a road through the camera. This learning is a policy.

### Workflow

For defining a regular workflow of reinforcement learning, the example of optimising the process of placing goods in a warehouse by a robotic arm can be used. The goal is to teach the robotic arm how to pick up items, and place them efficiently and accurately in the desired locations within the warehouse.

#### Setting the environment
This includes the robotic arm, the warehouse layout, the goods to be placed, and the target locations for each item.

#### State representations
For the robotic arm, the state can include information, such as the position and orientation of the arm, the position of the items to be picked up, and the positions of the target locations.

#### Action space

Action spaces are the possible actions the robotic arm can take in each state.

#### Rewards and penalty

The robotic arm should be rewarded when it successfully places an item in the correct location and penalised for dropping items, damaging goods, or failing to place items accurately.

#### Training

The robotic arm starts in a random state and takes actions in the environment. Initially, it explores different actions randomly and observes the rewards and penalties it receives for each action. As it learns, it starts to prioritize actions that lead to higher rewards and avoids actions that result in penalties. Through multiple training iterations, the robotic arm learns better strategies for picking up and placing items in the warehouse.


