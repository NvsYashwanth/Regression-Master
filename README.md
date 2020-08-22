# Linear Regression
### `Linear Regression is a supervised machine learning algorithm that predicts a continuous output`

## Prediction Model
* We define the linear relationship for a given dependent variable `y` as ouput and the independent variable `x`as input. The model tries to fit a straight line by predicting the coefficients `m`(slope) and `b`(intercept or the bias term) where variables `m` and `b` are optimized to produce accurate predictions.
<p align='center'>
  <img src="https://github.com/NvsYashwanth/Sales-prediction/blob/master/assets/simple%20regression.png">
</p>

***The predictions can be modelled as*** :
<p align='center'>
  <img src='https://github.com/NvsYashwanth/Sales-prediction/blob/master/assets/general%20pred.png'>
</p>

***In vectorized form*** :
<p align='center'>
  <img src='https://github.com/NvsYashwanth/Sales-prediction/blob/master/assets/general%20vector%20pred.png'>
</p>

## Training
### ***For small number of features***
### Normal Equation
* Also regarded as the closed form.
<p align='center'>
  <img src='https://github.com/NvsYashwanth/Sales-prediction/blob/master/assets/normal%20eq.png'>
</p>

`Complexity is : O(n**3)`

### Pseudoinverse
* LinearRegression() of the scikit learn computes pseudoinverse using SVD (Singular Value Decomposition). This computationally efficient than Normal Equation especially when the matrix X is not invertible (singular).

`Complexity is : O(n**2)`

### ***For large number of features ~100,000***
### Gradient Descent
* Gradient descent is an optimization algorithm used to minimize some function (here in our case cost function that describes error) iteratively by moving in the negative direction of the gradient. 
* To undestand this algorithm, let us consider the case of a man trying to get to the bottom of the valley. 
<p align='center'>
  <img src=''>
</p>

* The best way to get down quickly is to move in the direction of the steepest slope. Gradient Desent achieves the same by measuring the local gradient of the error function and goes in the direction of descending gradient. Our goal is to reach the global minimum.
<p align='center'>
  <img src=''>
</p>

* The algorithm calculates the gradient or partial derivatives of the cost function w.r.t every parameter. This new gradient tells us the slope of our cost function at our current position (current parameter values) and the direction we should move to update our parameters. The size of our update is controlled by the learning rate.
* With a high learning rate we can cover more ground each step, but we risk overshooting the lowest point since the slope of the hill is constantly changing. 
<p align='center'>
  <img src=''>
</p>

* With a very low learning rate, we can confidently move in the direction of the negative gradient since we are recalculating it so frequently. A low learning rate is more precise, but calculating the gradient is time-consuming, so it will take us a very long time to get to the bottom.
<p align='center'>
  <img src=''>
</p>

* As mentioned before our goal is to reach the global minimum. But at times when our cost function has irregular cruve, with random initialization in place, one might reach a local minimum, which is not as good as the global minimum. 

* One way to overcome this is by using the concept of [momentum](https://distill.pub/2017/momentum/).
## Cost Function
* Cost function tells us how good our model is at making predictions. It has its own curve and gradient.
* For the Linear Regression model, we define the cost funciton MSE (Mean Square Error) that measures the average squared differnce between actual and predicted values. Our goal is to minimize this cost function in order to improve the accuracy of the model. It is a convex function, which means that line joining any given 2 points on this never has a local minimum. Only a global minimum.

<p align='center'>
  <img src='https://github.com/NvsYashwanth/Sales-prediction/blob/master/assets/MSE.png'>
</p>

* 
<p align='center'>
  <img src=''>
</p>



## Hypothesis
1. There exists a linear relationship between target and feature variables. This can be verified using scatterplots.
2. There is little or no multicollinearity between feature variables. The same can be checked using pariplot and heatmaps.
3. Error terms are normally distributed. Perform residual analysis to verify the same.
