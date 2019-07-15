# Task 1


### Biased and Unbiaseds

In statistics, the bias (or bias function) of an estimator is the difference between this estimator's expected value and the true value of the parameter being estimated. An estimator or decision rule with zero bias is called unbiased. Otherwise the estimator is said to be biased.

* When we divide by (n −1) when calculating the sample variance, then it turns out that
  the average of the sample variances for all possible samples is equal the population variance.
  So the sample variance is what we call an unbiased estimate of the population variance.



$$\delta^2 = \frac{1}{n-1} \sum_{i=1}^{n} (x_i -\bar{x})^2 $$

$\delta$ = sample standard deviation

n = count of values in sample

$x_i$ can represent any value in the sample

$\bar{x}$ is the sample mean


* If instead we were to divide by n when calculating the sample variance,
  then the average for all possible samples would NOT equal the population variance.
  Dividing by n does not give an “unbiased” estimate of the population standard deviation.
  
  

$$\sigma^2 = \frac{1}{N} \sum_{i=1}^{N} (x_i -\mu)^2 $$



$\sigma$ = population standard deviation

N = count of values in population

$x_i$ can represent any value in the population

$\mu$ is the population mean
  
  


Example :
for [0,2,4]
Population mean = 0+2+4/3 = 2

Average of all sample variances with (n-1) is =8/3

average of all sample variances divided by (n) = 4/3

which is not equal.



# Task 2


Definition :
Covariance is a measure of the extent to which corresponding elements from two sets of ordered data move in the same direction. We use the following formula to compute covariance.

$$Cov(X,Y) = \frac{\sum(x_i -\bar{x})(y_j -\bar{y})}{n-1} $$


Cov(X, Y) = Σ ( Xi - Xm) ( Yi - Ym ) / N
Cov (X) = E (E(X - Xm)’ * E(X - Xm))

here X is the dataset 

Xm is the mean of corresponding columns or variables, similarly for y . 

E is the mean.

In Python the covariance matrix can be easily computed with a numpy function using "np.cov" .

To understand the method, a function can be made in Python to calculate covariance matrix. 
The function can be made using formula:

***Cov(X, Y) = Σ ( Xi - X ) ( Yi - Y ) / N = Σ xiyi / N.***

def cov(x,y):

    if len(x) != len(y):
        return

    n = len(x)

    xy = [x[i]*y[i] for i in range(n)]

    mean_x = sum(x)/float(n)
    mean_y = sum(y)/float(n)

    return (sum(xy) - n*mean_x * mean_y) / float(n)

x = [1,4,7]
y = [7,4,1]

print ('Unknown Covariance found another way is: : ' + str(cov(x,y)) )
