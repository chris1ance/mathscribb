# Notation

* $P(A)$: The probability of some event $A$ occuring

* $p_X(x) \equiv p(x) \equiv P(X = x)$: The PMF of a discrete rv $X$

* $f_X(x) \equiv f(x)$: The PDF of a continuous rv $X$

* $p(x)$: When referring to a random variable $X$ that can be either discrete or continuous, $p(x)$ is a useful shorthand to denote the PMF of $X$ if $X$ is discrete, or the PDF if $X$ is continuous.

* $\theta$: The parameters of the distribution of $X$. For example, if $X \sim N(\mu,\sigma^2)$, then $\theta = (\mu,\sigma^2)$

* $p_{\theta}(x) \equiv p(x|\theta) \equiv p(x;\theta)$: When referring to a random variable $X$ that can be either discrete or continuous, $p_{\theta}(x)$ is a useful shorthand to denote the PMF of $X$ if $X$ is discrete, or the PDF if $X$ is continuous.


# Sample Space

The set of possible outcomes is called the sample space. We will typically denote an individual outcome by $\omega$ and the sample space by $\Omega$.

# Sigma Algebra (a.k.a $\sigma$-algebra, sigma field)

Let $\mathcal{X}$ be a set. A collection $\mathcal{F}$ of subsets of $\mathcal{X}$ is called a **sigma algebra** if it satisfies the following three conditions:

1. **Non-emptiness**: $\emptyset \in \mathcal{F}$.
2. **Closed under complements**: If $A \in \mathcal{F}$, then the complement of $A$ (relative to $\mathcal{X}$), denoted $A^c = X \setminus A$, is also in $\mathcal{F}$.
3. **Closed under countable unions**: If $\{A_n\}_{n=1}^\infty$ is a sequence of sets in $\mathcal{F}$, then the union $\bigcup_{n=1}^\infty A_n$ is also in $\mathcal{F}$.

These properties imply several other characteristics:

- **Closed under countable intersections**: Using De Morgan's laws and the properties of sigma algebras, if $\{A_n\}_{n=1}^\infty$ are in $\mathcal{F}$, then $\bigcap_{n=1}^\infty A_n = (\bigcup_{n=1}^\infty A_n^c)^c$ is also in $\mathcal{F}$.
- **Contains the universal set**: Since $\emptyset \in \mathcal{F}$ and using the closure under complements, $X = \emptyset^c \in \mathcal{F}$.

There are two extreme examples of $\sigma$-algebras:
1. The collection $\{\emptyset,\mathcal{X}\}$, often called the trivial $\sigma$-algebra
2. The set $\mathcal{P}(\mathcal{X})$ of all subsets of $\mathcal{X}$, often called the full $\sigma$-algebra.
Any sigma-algebra $\mathcal{F}$ of subsets of $\mathcal{X}$ lies between these two extremes.

Note: Oftentimes, $\Sigma$ is used instead of $\mathcal{F}$ to denote a sigma-algebra

# Borel Sigma Algebra

If $\mathcal{X}$ is a set, the Borel $\sigma$-algebra, denoted $Bor(\mathcal{X})$, is defined as the $\sigma$-algebra generated by the collection of all open subsets of $\mathcal{X}$. The subsets of $X$ that belong to $Bor(X)$ are called Borel subsets of $X$.

Proposition: The $\sigma$-algebra on $\mathbb{R}$ generated by the open intervals of $\mathbb{R}$ is the Borel $\sigma$-algebra on $\mathbb{R}$.

# Measurable Space

A measurable space is a pair $(\mathcal{X},\mathcal{B})$ where $\mathcal{X}$ is a set and $\mathcal{B}$ is a $\sigma$-algebra of subsets of $\mathcal{X}$. 

# Probability Measure

Let $\mathcal{F}$ be a $\sigma$-field of events in $\Omega$. A probability measure on $\mathcal{F}$ is a real-valued function $P$ on $\mathcal{F}$ with the following properties.

1. $P(A) \geq 0$, for $A \in \mathcal{F}$.
2. $P(\Omega) = 1$, $P(\emptyset) = 0$.
3. If $A_n \in \mathcal{F}$ is a disjoint sequence of events, i.e., $A_i \cap A_j = \emptyset$ for $i \neq j$, then
$$
P\left(\bigcup_{n=1}^{\infty} A_n\right) = \sum_{n=1}^{\infty} P(A_n)
$$

# Probability Space

We refer to the triple $(\Omega, \mathcal{F}, P)$ as a probability space, where $\Omega$ is a sample space, $\mathcal{F}$ is a $\sigma$-algebra, and $P$ is a probability measure.

Theorem: Let $(\Omega, \mathcal{F}, P)$ be a probability space.

1. $P(A^c) = 1 - P(A)$ for $A \in \mathcal{F}$.
2. $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ for $A, B \in \mathcal{F}$.
3. $P(A | B) = \frac{P(A \cap B)}{P(B)}$ for $A, B \in \mathcal{F}$.
4. If $A \subseteq B$, then $P(A) \leq P(B)$ for $A, B \in \mathcal{F}$.
5. If $A_1, A_2, \ldots, A_n \in \mathcal{F}$ are disjoint, then
$$
P\left(\bigcup_{j=1}^{n} A_j\right) = \sum_{j=1}^{n} P(A_j)
$$

# Random Variable

A random variable $X$ is a mapping:

$$ X: \Omega \rightarrow \mathbb{R} $$
that assigns a real number $X(\omega)$ to each outcome $\omega$.

# Cumulative distribution function (CDF)

The cumulative distribution function, or cdf, of a random variable $X$ is the function $F_X : \mathbb{R} \rightarrow [0,1]$ defined by

$$ F_X(x) = P(X \leq x) $$
Sometimes we write the CDF as $F$ instead of $F_X$.

__Theorem:__ Let $X$ have CDF $F$ and let $Y$ have CDF $G$. If $F(x)=G(x)$ for all $x$, then $P(X \in A) = P(Y \in A)$ for all $A$.

__Theorem:__ A function $F$ mapping the real line to $[0, 1]$ is a cdf for some probability $P$ if and only if $F$ satisfies the following three conditions:
1. $F$ is non-decreasing: $x_1 < x_2$ implies $F(x_1) \leq F(x_2)$
2. $F$ is normalized: $\underset{x \rightarrow - \infty}{lim} F(x) = 0$ and $\underset{x \rightarrow  \infty}{lim} F(x) = 1$
3. $F$ is right-continuous: $F(x) = F(x^{+})$ for all $x$, where $F(x^{+}) = \underset{x \rightarrow  y, \ y > x}{lim} F(y)$

# Discrete Random Variable

$X$ is discrete if it takes countably many values $\{x_1,x_2,...\}$. We define the probability function or probability mass function for $X$ by

$$f_X(x) = P(X=x)$$

The CDF of $X$ is related to $f_X$ by

$$F_X(x) = P(X \leq x) = \sum_{x_i \leq x} f_X(x_i) $$


# Continuous Random Variables

## Univariate

Let $X$ be a random variable which takes values $x \in \mathcal{X} \subseteq \mathbb{R}$.

A function $f: \mathcal{X} \rightarrow \mathbb{R}$ is called a probability density function (pdf) if:

1. $\forall x \in \mathcal{X}: \ f(x) \geq 0$
2. The integral exists and $$\int f(x) d x = 1$$where the integral is taken over $\mathcal{X}$.

A common notion for the pdf is $f_X(x)$, but often the $X$ is suppressed in the notation. 

We associate a random variable $X \in \mathbb{R}$ with this function $f$ by 
$$p(a \leq X \leq b) = \int_a^b f(x) dx$$
where $a \in \mathbb{R}$ and $b \in \mathbb{R}$ are scalars, and where $x \in \mathbb{R}$ is an outcome of the continuous random variable $X$. 

In addition: $p(X = x) = 0$ for all $x$.

A cumulative distribution function (cdf) is given by:

$$ F_X(x) = P(X \leq x) = \int_{-\infty}^x f(z) dz $$

Warning: Don't try to think of $f(x)$ as $P(X=x)$. This only holds for discrete random variables. We get probabilities from a pdf by integrating. A pdf can be bigger than 1 (unlike a mass function). In fact, a pdf can be unbounded.

## Multivariate

A multivariate random variable is a vector $X = (X_1, X_2, \dots, X_n)$, where each component $X_i$ is itself a continuous random variable, and the vector $\mathbf{x}$ takes values in $\mathcal{X} \subseteq \mathbb{R}^n$.

A function $f: \mathcal{X} \rightarrow \mathbb{R}$ is called a multivariate probability density function (pdf) if it satisfies:

1. $\forall \mathbf{x} \in \mathcal{X}: \ f(\mathbf{x}) \geq 0$
2. The integral over the entire space exists and $$ \int f(\mathbf{x}) d \mathbf{x} = 1$$where the integral is taken over $\mathbb{R}^n$, the space $\mathcal{X}$ resides in.

A common notion for the pdf is $f_{X_1, X_2, \dots, X_n}(\mathbf{x})$, but often the $X_1,...,X_n$ is suppressed in the notation. 

The joint pdf, $f(\mathbf{x})$, describes the probability density associated with the random variables simultaneously assuming the values specified by $\mathbf{x}$. From the joint distribution, we can derive the marginal distribution of any subset of these variables by integrating out the other variables. For example, the marginal pdf of $X_1$ is given by:

$$ f_{X_1}(x_1) = \int_{x_2} \dots \int_{x_n} f(\mathbf{x}) d x_2 \dots d x_n $$

where $\int_{x_i}$ denotes the integral take with respect to $X_i$.

The joint cumulative distribution function (cdf) for a multivariate random variable $\mathbf{X}$ is defined as:

$$ F(\mathbf{x}) \equiv F_{X_1,...,X_n}(\mathbf{x}) = \int_{-\infty}^{x_1} \dots \int_{-\infty}^{x_n} f(\mathbf{z}) d\mathbf{z} $$

# Conditional Probability

__Definition__: 

$$p(A|B) = \frac{p(A,B)}{p(B)}$$

__Product Rule:__ 

$$ p(A,B) = p(A|B)p(B) $$

$$ p(X,Y|Z) = p(X|Y,Z)p(Y|Z) $$

$$p(X,Y,Z) = p(X,Y|Z)p(Z) = p(X|Y,Z)p(Y|Z)p(Z)$$

__Chain Rule:__

$$p(x_1,...,x_N) = p(x_1) \prod_{i=2}^N p(x_i|x_{<i})$$

# Sum Rule (Marginalization)

If $Y$ is discrete:

$$p(\mathbf{x}) = \sum_{\mathbf{y} \in \mathcal{Y}} p(\mathbf{x},\mathbf{y})$$

If $Y$ is continuous:

$$p(\mathbf{x}) = \int_{\mathcal{Y}} p(\mathbf{x},\mathbf{y}) d\mathbf{y} $$

$$ 
p(\mathbf{x}|\mathbf{z}) = 
\int_{\mathcal{Y}} p(\mathbf{x},\mathbf{y}|\mathbf{z}) d \mathbf{y} = 
\int_{\mathcal{Y}} p(\mathbf{x}|\mathbf{y}, \mathbf{z}) p(\mathbf{y}|\mathbf{z}) d \mathbf{y}
$$

# Bayes' Theorem

If $A$ and $B$ are events and $p(A) > 0$ and $p(B) >0$, then:

$$p(B|A) = \frac{p(A|B)p(B)}{\int_{B} p(A|B)p(B) dB} = \frac{p(A|B)p(B)}{p(A)} =  \frac{p(A,B)}{p(A)}$$

# Law of Total Probability

## Discrete Random Variables

For discrete random variables, suppose we have a finite or countably infinite partition of the sample space, $\{B_n\}_{n=1}^\infty$, such that $$\sum_{n=1}^\infty P(B_n) = 1$$ and $$P(B_n) > 0$$ for all $n$. 

Let $A$ be any event. The Law of Total Probability states that:

$$
P(A) = \sum_{n=1}^\infty P(A \mid B_n) P(B_n)
$$

This equation means that the probability of $A$ is the sum of the probabilities of $A$ occurring given each event $B_n$, each weighted by the probability of $B_n$ occurring.

## Continuous Random Variables

For continuous random variables, the partition of the sample space is typically represented by a continuous variable. If $Y$ is a continuous random variable and $A$ is an event, then the law can be written in terms of the density function $f_Y(y)$. Let $B$ be a subset of the range of $Y$ such that $P(Y \in B) = 1$. Then:

$$
P(A) = \int_{B} P(A \mid Y=y) f_Y(y) \, dy
$$

# Expectation

## Discrete

The expectation, or expected value, of some function $g()$ of a discrete random variable $X \sim p$ is defined as

$$ \mathbb{E}_{X \sim p}[g(x)] = \sum_{x \in \mathcal{X}} g(x)P(X = x) $$

## Continuous

The expectation, or expected value, of some function $g()$ of a continuous random variable $X \sim f$ is defined as

$$ \mathbb{E}_{X \sim f}[g(x)] = \int g(x)f(x) dx $$

# Marginal Distribution

## Discrete

Suppose two discrete random variables $(X,Y)$ have joint PMF $p_{X,Y}(x,y)$. 

Then the marginal distribution of $X$ is the PMF $p_X(x)$, which is equal to:

$$ p_{X,Y}(x,y) = \sum_{y \in \mathcal{Y}} p_{X,Y}(X=x,Y=y) $$

## Continuous

Suppose two continuous random variables $(X,Y)$ have joint PDF $f_{X,Y}(x,y)$. 

Then the marginal distribution of $X$ is the PDF $f_X(x)$, which is equal to:

$$ f_X(x) = \int  f_{X,Y}(x,y) dy$$