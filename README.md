Classify
========

scikit-learn toolkit is being used to perform all the operations. 

Supplied data has 4 categories or labels - 0, 1, 2 and 3.

KDE plot of the data shows that labels 0 and 3 are not cleanly linearly separable.
Some of the data with labels 0 and 3 lying in the overlapping region will
always be misclassified. Though the Gaussian peak region is linearly separable
for labels 0 and 3.


Data is split into training and test set.
70% of the data is set aside for training and the rest for testing.

Features are standardized. 
For instance many elements used in the objective function of a learning algorithm (such as the
RBF kernel of Support Vector Machines or the L1 and L2 regularizers of linear models) assume 
that all features are centered around 0 and have variance in the same order.
If a feature has a variance that is orders of magnitude larger that others, it might dominate
the objective function and make the estimator unable to learn from other features correctly as expected.

By and large features are linearly separable. Since this is a multiclass
classification task, Logistic regression classification model is choosen. It's
a linear binary classification model using one-vs-rest scheme.

Parameters:

- lbfgs is the optimization method for finding a minimum of the objective
  function.
- The loss minimised is the Multinomial Loss fit across the entire probability distribution.
  So the objective function is Multinomila Logistic Loss function.
- Default l2 regularization is used for lbfgs.

Just for comparison purposes C-Support Vector Classification model is used.
But the best result I got from SVM model matches the one from Logistic Regression model used
before.

Parameters:

- Default kernel used is RBF.
- C is the penalty parameter - 100. This parameter controls the width of the
  margin and hence tune the bias-variance tradeoff.
- Gamma is 0.0001
- Kernel coeff is auto.

Since SVC model gives microscopically better result than Logistic Regression model,
model I went with the SVC model. For all practical purposes the results will be
similar as is obvious from the accuracy scores. 







