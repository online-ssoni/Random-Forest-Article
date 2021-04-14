# Random Forest

In the family of supervised learning algorithms, there are many techniques to perform the classification or regression over the training set. The machine learning technique that we apply to solve a problem often result in a single model. We are basically dependent on this model for all our results. The best we can do is to tune the hyperparameters.
But what if we could combine different types of models and arrive at an ensemble model which takes care of the weak areas of the single model?

With the concept of decision trees and the concept of ensemble in machine learning landscape, we will create this super model.

Ensemble Methods
According to Wikipedia, let’s first understand the meaning of ensemble,
In statistics and machine learning, ensemble methods use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms alone.

Decision Trees
Although this article assumes the prior knowledge of decision trees, let’s formally define the decision trees anyway.
A decision tree is a tree-like graph with nodes representing the place where we pick an attribute and ask a question; edges represent the answers the to the question; and the leaves represent the actual output or class label. They are used in non-linear decision making with simple linear decision surface.
 

Random Forests
The random forest is a supervised learning algorithm consisting of many decisions trees. 
Each individual tree in the random forest spits out a class prediction and the class with the most votes becomes our model’s prediction

 

A random forest is almost always better than a single decision tree. 
In principle, ensembles can be made by combining all types of models. An ensemble can have a logistic regression, a neural network, and few decision trees working in unison.

How the individual tree is created in random forest?
It uses bagging and feature randomness when building each individual tree to try to create an uncorrelated forest of trees whose prediction by committee is more accurate than that of any individual tree.

Bagging
Bootstrap Aggregation (or Bagging for short), is a simple and very powerful ensemble method. It is a technique for choosing random samples of observations from a dataset. Each of these samples is then used to train each tree in the forest.
Decision trees are sensitive to the specific data on which they are trained. If the training data is changed (e.g. a tree is trained on a subset of the training data) the resulting decision tree can be quite different and in turn the predictions can be quite different.
We train a number of decision trees from bootstrap (random) samples of your training set. After we have created M different models, we use aggregated output of the M different models as our ensemble output.


Diversity & Acceptability 
Diversity ensures that the models serve complementary purposes, which means that the individual models make predictions independent of each other. The advantages of this are different depending on the type of ensemble.

Acceptability implies that each model is at least better than a random model. This is a pretty lenient criterion for each model to be accepted into the ensemble, i.e. it has to be at least better than a random guesser.

Ensembles avoid getting misled by the assumptions made by individual models.

In a binary classification task, an ensemble makes decisions by taking the majority vote. This means that if there are n models in the ensemble, and more than half of them give you the right answers, you will make the right decision; if more than n/2 are wrong, you will make a wrong decision. In the coin toss analogy, making a correct prediction corresponds to head, whereas getting a wrong prediction corresponds to tail.


Advantages of Random Forest
•	It reduces overfitting in decision trees and helps to improve the accuracy
•	A random forest has a lower model variance than an ordinary individual tree.
•	It is flexible to both classification and regression problems
•	It works well with both categorical and continuous values
•	It automates missing values present in the data
•	Normalising of data is not required as it uses a rule-based approach
•	Immunity to the curse of dimensionality: Since each tree does not consider all the features, the feature space (the number of features a model has to consider) reduces. This makes the algorithm immune to the curse of dimensionality. A large feature space causes computational and complexity issues
•	Parallelizability: You need a number of trees to make a forest. Since two trees are independently built on different data and attributes, they can be built separately. This implies that you can make full use of your multi-core CPU to build random forests. Suppose there are 4 cores and 100 trees to be built; each core can build 25 trees to make a forest

Disadvantages of Random Forest
•	It requires much computational power as well as resources as it builds numerous trees to combine their outputs.
•	It also requires much time for training as it combines a lot of decision trees to determine the class.
•	Due to the ensemble of decision trees, it also suffers interpretability and fails to determine the significance of each variable.

We will now build a random forest model to predict whether a given customer defaults or not. Credit default is one of the most important problems in the banking and risk analytics industry. There are various attributes which can be used to predict default, such as demographic data (age, income, employment status, etc.), (credit) behavioural data (past loans, payment, number of times a credit payment has been delayed by the customer etc.).
