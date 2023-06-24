This document records some references of important lemmas and theorems in statistics. Some applications are also provided. 

 - 这里主要记录可能有必要引用的参考文献，一些耳熟能详，人尽皆知，脍炙人口的定理（如Taylor expansion, Cauchy-Schwarz inequality, Holder inequality, Dominated Convergence Theorem...）可能就被选择性地掠过了
 - 参考文献格式来自Google Scholar，可能有书籍的年份问题，建议以论文中常见的引用格式为主
 - 暂时未考虑按照什么顺序展示较好，如有更好的提议，欢迎提出！
 - 本处只提供参考文献名，具体的pdf自行搜索。

### Generalized Linear Model

- McCullagh, P. and Nelder, J. A. (2019), Generalized linear models, Routledge, New York.

### Inequality

#### One-sided Chebyshev inequality

- Ross, S. (2010). A first course in probability. Pearson.

#### Concentration inequalies (mainly for non-asymptotic results)

- Vershynin, R. (2018). High-dimensional probability: An introduction with applications in data science (Vol. 47). Cambridge university press.
- Wainwright, M. J. (2019). High-dimensional statistics: A non-asymptotic viewpoint (Vol. 48). Cambridge university press.

### Asymptotic Theory (e.g. LLN and CLT)

- Shao, J. (2003). Mathematical statistics. Springer Science & Business Media.

- Serfling, R. J. (2009). Approximation theorems of mathematical statistics. John Wiley & Sons.

- Van der Vaart, A. W. (2000). Asymptotic statistics (Vol. 3). Cambridge university press.

This book records various topics of statistics. Highly recommanded !!

- Newey, W. K., & McFadden, D. (1994). Large sample estimation and hypothesis testing. Handbook of econometrics, 4, 2111-2245.

#### Local consistency and rate of convergence in parametric model

- Fan, J., & Li, R. (2001). Variable selection via nonconcave penalized likelihood and its oracle properties. Journal of the American statistical Association, 96(456), 1348-1360.

This technique is generalized to the case of diverging dimensional in the following article.

- Fan, J., & Peng, H. (2004). Nonconcave penalized likelihood with a diverging number of parameters. Annals of statistics, 32(3), 928-961.

Note: Local consistency means there exists a local maximizer such that the estimator will convergence in probability to it. Given the loss function is convex, the local maxima is also the global maxima. The local consistency is just the global consistency. While for nonconvex loss function, the local maxima might not be the global maxima, this method might not be used in such cases.

### Martingale CLT 

This theorem is commonly used in time series analysis and high dimensional hypothesis testing. 

- Hall, P., & Heyde, C. C. (2014). Martingale limit theory and its application. Academic press.

#### Some applications

- Chen, S. X., & Qin, Y. L. (2010). A two-sample test for high-dimensional data with applications to gene-set testing. The Annals of Statistics, 38(2), 808-835.

This paper constructs a martingale difference sequences to prove the asymptotic normality of the test statistic based on high dimensional data. 

- Zhu, X., Pan, R., Li, G., Liu, Y., & Wang, H. (2017). Network vector autoregression. The Annals of Statistics, 45, 1096-1123.

### Empirical Process Theory

Empirical process theory is widely used in econometrics and statistics. However, this theory might be much more abstract and mathematical than other fields in statistics. More efforts should be paid if you want to master the knowledge.

- Van Der Vaart, A. W., Wellner, J. A., van der Vaart, A. W., & Wellner, J. A. (1996). Weak convergence and empirical process. Springer New York.
- Kosorok, M. R. (2008). Introduction to empirical processes and semiparametric inference. New York: Springer.

#### Applications in non-differentiable objective functions
- Newey, W. K., & McFadden, D. (1994). Large sample estimation and hypothesis testing. Handbook of econometrics, 4, 2111-2245.
- Chen, X., Linton, O., & Van Keilegom, I. (2003). Estimation of semiparametric models when the criterion function is not smooth. Econometrica, 71(5), 1591-1608.

#### Applications in nonparametric estimation
- Han, Q., Wang, T., Chatterjee, S., & Samworth, R. J. (2019). Isotonic regression in general dimensions. Annals of Statistics, 47(5), 2440-2471.
- Schmidt-Hieber, J. (2020). Nonparametric regression using deep neural networks with ReLU activation function. Annals of Statistics, 48(4), 1875-1897


### Time Series Analysis

### Model Averaging

### Random Matrix Theory

### Feature Screening

### Factor Model

### Quantile Regression

### Some Important Results for Matrices

### Weakly Dependent Data

### Bootstrap

### To Be Continued...
