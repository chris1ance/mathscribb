# Maximum Likelihood

Let $X_1,...,X_n$ be IID with PDF $f(x;\theta)$. The __likelihood function__ is defined by

$$ \mathcal{L}_n(\theta) = \prod_{i=1}^n f(X_i; \theta) $$

The __log-likelihood function__ is defined by 

$$ \ell _n(\theta) = \log \mathcal{L}_n(\theta)$$

The maximum likelihood estimator MLE, denoted by $\hat{\theta}_n$, is the value of $\theta$ that maximizes $\mathcal{L}_n(\theta)$.

Properties:

1. $$ \hat{\theta}_n = \underset{\hat{\theta}}{argmax} \ \mathcal{L}_n(\theta) = \underset{\hat{\theta}}{argmax} \ \ell _n(\theta) = \underset{\hat{\theta}}{argmin} \ -\mathcal{L}_n(\theta) = \underset{\hat{\theta}}{argmin} \ -\ell _n(\theta) $$