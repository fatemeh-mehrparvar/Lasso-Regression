# Lasso-Regression
"Lasso Regression model for feature selection"

Lasso regression—also known as L1 regularization—is a form of regularization for linear regression models.
Regularization is a statistical method to reduce errors caused by overfitting on training data. 

This approach can be reflected with this formula: 

w-hat = argminw MSE(W ) + ||w||1 

Lasso stands for Least Absolute Shrinkage and Selection Operator. 
It is frequently used in machine learning to handle high dimensional data as it facilitates automatic feature selection with its application. 
It does this by adding a penalty term to the residual sum of squares (RSS), which is then multiplied by the regularization parameter (lambda or λ).
This regularization parameter controls the amount of regularization applied. 
Larger values of lambda increase the penalty, shrinking more of the coefficients towards zero; this subsequently reduces the importance of (or altogether eliminates) some of the features from the model, resulting in automatic feature selection. Conversely, smaller values of lambda reduce the effect of the penalty, retaining more features within the model.

 
RSS=Σ(yᵢ−y^ᵢ)²

Where,yi is the observed value.
and y^ᵢ is the predicted value for each data point i.

RSS+λ×∑∣βi∣

Where,βi represents the coefficients of the predictors
and λ is the tuning parameter that controls the strength of the penalty. 
As lambda increases, more coefficients are pushed towards zero.

This penalty promotes sparsity within the model, which can help avoid issues of multicollinearity and overfitting issues within datasets.
Multicollinearity occurs when two or more independent variables are highly correlated with one another, which can be problematic for causal modeling. 
Overfit models will generalize poorly to new data, diminishing their value altogether. 
By reducing regression coefficients to zero, lasso regression can effectively eliminate independent variables from the model, sidestepping these potential issues within modeling process. Model sparsity can also improve the interpretability of the model compared to other regularization techniques such as ridge regression (also known as L2 regularization).
As a note, this article focuses on regularization of linear regression models, but it’s worth noting that lasso regression may also be applied in logistic regression.

"Fit the lasso model and choose a value for λ"

Fit the lasso regression model on the training data and choose a value for λ with the objective of minimizing the mean squared error (MSE).
The mean square error (MSE) can help determine a suitable λ value. 
MSE is a means of measuring the difference, on average, between predicted and true values of the dependent variable. Lasso regression minimizes the mean squared error (MSE) while balancing the opposing factors of bias and variance to build the most accurate predictive model.
It achieves this by adding a penalty term to the residual sum of squares (RSS) equal to the sum of the absolute values of the coefficients multiplied by a parameter λ.

"Optimize for λ with cross-validation"

The optimal value of λ can be determined with cross-validation techniques, such as k-fold cross-validation; this approach finds the λ value that minimizes the mean squared error or other performance metrics.
As noted previously, a higher λ value applies more regularization. As λ increases, model bias increases while variance decreases. This is because as λ becomes larger, more coefficients 𝛽 shrink to zero.
