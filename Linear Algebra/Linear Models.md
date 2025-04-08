# Linear Models

Define:

- **Observables**: $\mathbf{Y} \in \mathbb{R}^{T \times N}$

    - Element: $y_{ti} \in \mathbb{R}$ where $t=1,...,T$ and $i=1,...,N$

    - Columns: $\mathbf{y}_{\cdot i} \in \mathbb{R}^{T \times 1}$

    - Rows: $\mathbf{y}_{t \cdot} \in \mathbb{R}^{N \times 1}$

- **Idiosyncratic errors/shocks**: $\mathbf{E} \in \mathbb{R}^{T \times N}$

    - Element: $e_{ti} \in \mathbb{R}$

    - Columns: $\mathbf{e}_{\cdot i} \in \mathbb{R}^{T \times 1}$

    - Rows: $\mathbf{e}_{t \cdot} \in \mathbb{R}^{N \times 1}$

Notes:
- $\mathbf{y}_{t} \equiv \mathbf{y}_{t \cdot}$, $\mathbf{e}_{t} \equiv \mathbf{e}_{t \cdot}$, and so on.

## VAR Models

Define:

- **Coefficients**: VAR(p) coefficient matrices are denoted by $\mathbf{a}_0, \mathbf{A}_1,..., \mathbf{A}_p$, where
    - $\mathbf{a}_0 \in \mathbb{R}^N$ is an intercept vector
    - $\mathbf{A}_j \in \mathbb{R}^{N \times N}$
    - $\mathbf{A} = [\mathbf{a}_0, \mathbf{A}_1, \mathbf{A}_2, ..., \mathbf{A}_p]$

Then the following are all equivalent expressions of the same model:

$$\mathbf{y}_{t} = \mathbf{a}_0 + \sum_{j=1}^p \mathbf{A}_j \mathbf{y}_{t-j} + \mathbf{e}_{t} \tag{1}$$

## Factor Models

Define:

- **Factors**: $\mathbf{F} \in \mathbb{R}^{T \times q}$

    - Element: $f_{tr} \in \mathbb{R}$

    - Columns: $\mathbf{f}_{\cdot r} \in \mathbb{R}^{T \times 1}$

    - Rows: $\mathbf{f}_{t \cdot} \in \mathbb{R}^{q \times 1}$

- **Loadings**: $\boldsymbol{\Lambda} \in \mathbb{R}^{N \times q}$ represents a matrix of weights.

    - Element: $\lambda_{ir} \in \mathbb{R}$

    - Columns: $\boldsymbol{\lambda}_{\cdot r} \in \mathbb{R}^{N \times 1}$

    - Rows: $\boldsymbol{\lambda}_{i \cdot} \in \mathbb{R}^{q \times 1}$

Then the following are all equivalent expressions of the same model:

$$y_{ti} = \mathbf{f}_{t \cdot}^T \boldsymbol{\lambda}_{i \cdot} + e_{ti} \tag{1}$$

$$\mathbf{y}_{t \cdot} = \boldsymbol{\Lambda} \mathbf{f}_{t \cdot} + \mathbf{e}_{t \cdot} \tag{2}$$

$$\mathbf{Y} = \mathbf{F} \boldsymbol{\Lambda}^T + \mathbf{E} \tag{3}$$

**Proof: Equivalence of (2) and (3)**

Since:

$$
\mathbf{F} \boldsymbol{\Lambda}^\top =

\begin{bmatrix}
    \mathbf{f}_{1 \cdot}^\top \boldsymbol{\Lambda}^\top \\
    \vdots \\
    \mathbf{f}_{T \cdot}^\top \boldsymbol{\Lambda}^\top
\end{bmatrix}
$$

We have that (3) is equivalent to:

$$
\begin{bmatrix} \mathbf{y}_{1 \cdot}^\top \\ \vdots \\ \mathbf{y}_{T \cdot}^\top \end{bmatrix} =

\begin{bmatrix}
    \mathbf{f}_{1 \cdot}^\top \boldsymbol{\Lambda}^\top \\
    \vdots \\
    \mathbf{f}_{T \cdot}^\top \boldsymbol{\Lambda}^\top
\end{bmatrix} +

\begin{bmatrix} \mathbf{e}_{1 \cdot}^\top \\ \vdots \\ \mathbf{e}_{T \cdot}^\top \end{bmatrix}
$$

Equivalently:

$$\mathbf{y}_{t \cdot}^\top = \mathbf{f}_{t \cdot}^\top \boldsymbol{\Lambda}^\top  + \mathbf{e}_{t \cdot}^\top$$

Which is equal to (2) after taking the transpose of both sides.


**Proof: Equivalence of (1) and (2)**

Since:

$$
\mathbf{F} \boldsymbol{\Lambda}^\top =

\begin{bmatrix}
    \mathbf{f}_{1 \cdot}^\top \boldsymbol{\Lambda}^\top \\
    \vdots \\
    \mathbf{f}_{T \cdot}^\top \boldsymbol{\Lambda}^\top
\end{bmatrix} =

[\mathbf{F} \boldsymbol{\lambda}_{1 \cdot} | \cdots | \mathbf{F} \boldsymbol{\lambda}_{q \cdot}] =

\begin{bmatrix}
\mathbf{f}_{1 \cdot}^T \boldsymbol{\lambda}_{1 \cdot} & \mathbf{f}_{1 \cdot}^T \boldsymbol{\lambda}_{2 \cdot} & \cdots & \mathbf{f}_{1 \cdot}^T \boldsymbol{\lambda}_{q \cdot} \\
\mathbf{f}_{2 \cdot}^T \boldsymbol{\lambda}_{1 \cdot} & \mathbf{f}_{2 \cdot}^T \boldsymbol{\lambda}_{2 \cdot} & \cdots & \mathbf{f}_{2 \cdot}^T \boldsymbol{\lambda}_{q \cdot} \\
\vdots & \vdots & \ddots & \vdots \\
\mathbf{f}_{T \cdot}^T \boldsymbol{\lambda}_{1 \cdot} & \mathbf{f}_{T \cdot}^T \boldsymbol{\lambda}_{2 \cdot} & \cdots & \mathbf{f}_{T \cdot}^T \boldsymbol{\lambda}_{q \cdot}
\end{bmatrix}
$$

We have that (3) is equivalent to:

$$ y_{ti} = \mathbf{f}_{t \cdot}^T \boldsymbol{\lambda}_{i \cdot} + e_{ti} $$

Which is just (1) restated.