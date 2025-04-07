# Multivariate Normal (MVN)

## Linear Gaussian Systems

Let $\mathbf{z} \in \mathbb{R}^L$ be an unknown vector of values, and $\mathbf{y} \in \mathbb{R}^D$ be some noisy measurement of $\mathbf{z}$. We assume these variables are related by the following joint distribution:

$$p(\mathbf{z}) = \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_z, \boldsymbol{\Sigma}_z)$$

$$p(\mathbf{y}|\mathbf{z}) = \mathcal{N}(\mathbf{y}|\mathbf{W}\mathbf{z} + \mathbf{b}, \boldsymbol{\Sigma}_y)$$

where $\mathbf{W}$ is a matrix of size $D \times L$. This is an example of a **linear Gaussian system**.

The corresponding joint distribution, $p(\mathbf{z}, \mathbf{y}) = p(\mathbf{z})p(\mathbf{y}|\mathbf{z})$, is a $L + D$ dimensional Gaussian, with mean and covariance given by

$$
\boldsymbol{\mu} = 
\begin{pmatrix} \boldsymbol{\mu}_z \\ \mathbf{W}\boldsymbol{\mu}_z + \mathbf{b} \end{pmatrix}
$$

$$
\boldsymbol{\Sigma} = 
\begin{pmatrix} \boldsymbol{\Sigma}_z & \boldsymbol{\Sigma}_z\mathbf{W}^{\top} \\ \mathbf{W}\boldsymbol{\Sigma}_z & \boldsymbol{\Sigma}_y + \mathbf{W}\boldsymbol{\Sigma}_z\mathbf{W}^{\top} \end{pmatrix}
$$

## Bayes rule for Gaussians

The posterior over the latent is given by

$$p(\mathbf{z}|\mathbf{y}) = \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_{z|y}, \boldsymbol{\Sigma}_{z|y})$$

$$\boldsymbol{\Sigma}^{-1}_{z|y} = \boldsymbol{\Sigma}^{-1}_z + \mathbf{W}^{\top}\boldsymbol{\Sigma}^{-1}_y\mathbf{W}$$

$$\boldsymbol{\mu}_{z|y} = \boldsymbol{\Sigma}_{z|y}[\mathbf{W}^{\top}\boldsymbol{\Sigma}^{-1}_y(\mathbf{y} - \mathbf{b}) + \boldsymbol{\Sigma}^{-1}_z\boldsymbol{\mu}_z]$$

This is known as **Bayes rule for Gaussians**. Furthermore, the normalization constant of the posterior is given by

$$p(\mathbf{y}) = \int \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_z, \boldsymbol{\Sigma}_z)\mathcal{N}(\mathbf{y}|\mathbf{W}\mathbf{z} + \mathbf{b}, \boldsymbol{\Sigma}_y)d\mathbf{z} = \mathcal{N}(\mathbf{y}|\mathbf{W}\boldsymbol{\mu}_z + \mathbf{b}, \boldsymbol{\Sigma}_y + \mathbf{W}\boldsymbol{\Sigma}_z\mathbf{W}^{\top})$$

We see that the Gaussian prior $p(\mathbf{z})$, combined with the Gaussian likelihood $p(\mathbf{y}|\mathbf{z})$, results in a Gaussian posterior $p(\mathbf{z}|\mathbf{y})$. Thus Gaussians are closed under Bayesian conditioning. To describe this more generally, we say that the Gaussian prior is a **conjugate prior** for the Gaussian likelihood, since the posterior distribution has the same type as the prior.

## Inference in the presence of missing data

Suppose we have a linear Gaussian system where we only observe part of $\mathbf{y}$, call it $\mathbf{y}_1$, while the other part, $\mathbf{y}_2$, is hidden:

$$p(\mathbf{z}) = \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_z, \boldsymbol{\Sigma}_z)$$

$$p\left(\begin{pmatrix} \mathbf{y}_1 \\ \mathbf{y}_2 \end{pmatrix}\bigg|\mathbf{z}\right) = \mathcal{N}\left(\begin{pmatrix} \mathbf{y}_1 \\ \mathbf{y}_2 \end{pmatrix}\bigg|\begin{pmatrix} \mathbf{W}_1 \\ \mathbf{W}_2 \end{pmatrix}\mathbf{z} + \begin{pmatrix} \mathbf{b}_1 \\ \mathbf{b}_2 \end{pmatrix}, \begin{pmatrix} \boldsymbol{\Sigma}_{11} & \boldsymbol{\Sigma}_{12} \\ \boldsymbol{\Sigma}_{21} & \boldsymbol{\Sigma}_{22} \end{pmatrix}\right)$$

We can compute $p(\mathbf{z}|\mathbf{y}_1)$ by partitioning the joint into $p(\mathbf{z}, \mathbf{y}_1, \mathbf{y}_2)$, marginalizing out $\mathbf{y}_2$, and then conditioning on $\mathbf{y}_1$. The result is as follows:

$$p(\mathbf{z}|\mathbf{y}_1) = \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_{z|1}, \boldsymbol{\Sigma}_{z|1})$$

$$\boldsymbol{\Sigma}^{-1}_{z|1} = \boldsymbol{\Sigma}^{-1}_z + \mathbf{W}^{\top}_1\boldsymbol{\Sigma}^{-1}_{11}\mathbf{W}_1$$

$$\boldsymbol{\mu}_{z|1} = \boldsymbol{\Sigma}_{z|1}[\mathbf{W}^{\top}_1\boldsymbol{\Sigma}^{-1}_{11} (\mathbf{y}_1 - \mathbf{b}_1) + \boldsymbol{\Sigma}^{-1}_z\boldsymbol{\mu}_z]$$

# References

- Kevin P. Murphy. "Probabilistic Machine Learning: An Introduction." Chapter 3, Section 3.