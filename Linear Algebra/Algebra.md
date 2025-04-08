# Notation

Matrices:
- $\mathbf{A} \in \mathbb{R}^{n \times m}$

    - Element: $a_{ij} \in \mathbb{R}$ where $i=1,...,n$ and $j=1,...,m$

    - Columns: $\mathbf{a}_{\cdot j} \in \mathbb{R}^{n \times 1}$

    - Rows: $\mathbf{a}_{i \cdot} \in \mathbb{R}^{m \times 1}$

$$
\mathbf{A} =
[\mathbf{a}_{\cdot 1} | \cdots | \mathbf{a}_{\cdot m}] = 
\begin{bmatrix} \mathbf{a}_{1 \cdot}^\top \\ \vdots \\ \mathbf{a}_{n \cdot}^\top \end{bmatrix} =
[a_{ij}]
$$

- $\mathbf{B} \in \mathbb{R}^{m \times p}$

# Dot Product

The dot product of  $n$-dimensional *column* $\mathbf{x}$ and $\mathbf{y}$ is:

$$ \mathbf{x} \cdot \mathbf{y} = \mathbf{x}^T \mathbf{y} = \mathbf{y}^T \mathbf{x} = \sum_{i=1}^n x_i y_i $$

# Outer Product

If $\mathbf{u}$ is an $n$-dimensional vector and $\mathbf{v}$ is an $m$-dimensional vector:

$$ 
\mathbf{u} \otimes \mathbf{v} = 
\mathbf{u} \mathbf{v}^T =
\begin{bmatrix}
u_1 \\
\vdots \\
u_n
\end{bmatrix}
\begin{bmatrix}
v_1 & \cdots & v_m
\end{bmatrix} = 
[v_1 \mathbf{u}, \cdots , v_m \mathbf{u}] = 
\begin{bmatrix}
u_1v_1 & u_1v_2 & \cdots & u_1v_m \\
u_2v_1 & u_2v_2 & \cdots & u_2v_m \\
\vdots & \vdots & \ddots & \vdots \\
u_nv_1 & u_nv_2 & \cdots & u_nv_m
\end{bmatrix}
$$

Source: https://en.wikipedia.org/wiki/Outer_product

A matrix $\mathbf{X}$ whose columns are equal to some vector $\mathbf{x}$, i.e. $\mathbf{X} = [\mathbf{x},\cdots,\mathbf{x}]$ can be compactly represented using an outer product as:

$$ \mathbf{X} = [\mathbf{x},\cdots,\mathbf{x}] = \mathbf{x} \mathbf{1}^T $$

# Matrix-Vector Products

**Case 1:**
If $\mathbf{x}$ is an $m$-dimensional column vector, then the matrix-vector product $\mathbf{A}\mathbf{x}$ is a linear combination of the column vectors of $\mathbf{A}$:

$$
\mathbf{A}\mathbf{x} = 
x_1\mathbf{a}_1 + \cdots + x_m\mathbf{a}_m = 
\sum_{j=1}^m x_j\mathbf{a}_j
$$

Equivalently:
$$
\mathbf{A}\mathbf{x} = 
\begin{bmatrix}
    \mathbf{a}_1^\top \mathbf{x} \\
    \vdots \\
    \mathbf{a}_n^\top \mathbf{x}
\end{bmatrix} =
\begin{bmatrix}
    \sum_{j=1}^m a_{1j} x_j \\
    \vdots \\
    \sum_{j=1}^m a_{nj} x_j
\end{bmatrix}
$$

Equivalently, if we define $\mathbf{z} = \mathbf{A} \mathbf{x}$, then we have that the $i^{th}$ element of $\mathbf{z}$ is:

$$ z_i = \sum_{j=1}^m a_{ij} x_j $$

**Case 2:**
If $\mathbf{x}$ is an $n$-dimensional column vector, then the matrix-vector product $\mathbf{x}^T\mathbf{A}$ is a linear combination of the row vectors of $\mathbf{A}$:

$$
\mathbf{x}^T\mathbf{A} = 
x_1\mathbf{a}_1^T + \cdots + x_n\mathbf{a}_n^T = 
\sum_{i=1}^n x_i\mathbf{a}_i^T
$$

Equivalently:

$$ \mathbf{x}^T\mathbf{A} = 
[\mathbf{x}^T \mathbf{a}_1, \cdots, \mathbf{x}^T \mathbf{a}_m] =
\Big[ \sum_{i=1}^n x_i a_{i1}, \cdots, \sum_{i=1}^n x_i a_{im} \Big] $$

**Other Special Products:**

Column $j$ of the matrix $\mathbf{A}$ is equal to

$$ \mathbf{a}_j = \mathbf{A} \mathbf{e}_j $$

where $\mathbf{e}_j \in \mathbb{R}^m$ is a column matrix with 1 in position $j$ and 0 everywhere else.

Row $i$ of the matrix $\mathbf{A}$ is equal to

$$ \mathbf{a}_i^T = \mathbf{e}_i^T\mathbf{A} $$

Equivalently:

$$ \mathbf{a}_i = \mathbf{A}^T \mathbf{e}_i $$

where $\mathbf{e}_i \in \mathbb{R}^n$ is a column matrix with 1 in position $i$ and 0 everywhere else.

## With Diagonal Matrices

If $\mathbf{D} = diag(d_1,\cdots,d_n)$, then:

$$ 
\mathbf{D} \mathbf{x} = 
\begin{bmatrix}
d_1 x_1 \\
\vdots \\
d_n x_n
\end{bmatrix}
$$

Source: https://en.wikipedia.org/wiki/Diagonal_matrix

# Matrix-Matrix Product

If $\mathbf{A} \in \mathbb{R}^{n \times m}$ and $\mathbf{B} \in \mathbb{R}^{m \times p}$, then:
$$ \mathbf{A}\mathbf{B} = \mathbf{C} \in \mathbb{R}^{n \times p}$$

Where:

$$
\mathbf{C} =

\begin{bmatrix}
    \mathbf{a}_1^\top \mathbf{B} \\
    \vdots \\
    \mathbf{a}_n^\top \mathbf{B}
\end{bmatrix} = 

[\mathbf{A} \mathbf{b}_1,\cdots,\mathbf{A} \mathbf{b}_p] =

\begin{bmatrix}
\mathbf{a}_1^T \mathbf{b}_1 & \mathbf{a}_1^T \mathbf{b}_2 & \cdots & \mathbf{a}_1^T \mathbf{b}_p \\
\mathbf{a}_2^T \mathbf{b}_1 & \mathbf{a}_2^T \mathbf{b}_2 & \cdots & \mathbf{a}_2^T \mathbf{b}_p \\
\vdots & \vdots & \ddots & \vdots \\
\mathbf{a}_n^T \mathbf{b}_1 & \mathbf{a}_n^T \mathbf{b}_2 & \cdots & \mathbf{a}_n^T \mathbf{b}_p
\end{bmatrix}
$$

That is, element $c_{ij}$ of $\mathbf{C}$ is equal to the dot product of the the $i^{th}$ row vector of $\mathbf{A}$ and the $j^{th}$ column vector of $\mathbf{B}$:

$$ c_{ij} = \mathbf{a}_i^T \mathbf{b}_j = \sum_{r=1}^m a_{ir} b_{rj} $$
which follows because $\mathbf{a}_i^T$ and  $\mathbf{b}_j$ are both in $\mathbb{R}^m$.


Equivalently:


$$
C = 

AB = 

\begin{bmatrix}
| & | & & | \\
\mathbf{a}_1 & \mathbf{a}_1 & \cdots & \mathbf{a}_m \\
| & | & & |
\end{bmatrix}
\begin{bmatrix}
- & \mathbf{b}_1^T & - \\
- & \mathbf{b}_2^T & - \\
& \vdots & \\
- & \mathbf{b}_m^T & -
\end{bmatrix} = 

\sum_{j=1}^m \mathbf{a}_j \mathbf{b}_j^T
$$

Source: CS224N Linear Algebra Review handout

## With Diagonal Matrices

If $\mathbf{D} = diag(d_1,\cdots,d_m)$, then:

$$ \mathbf{A} \mathbf{D} = [d_1 \mathbf{a}_1, \cdots , d_m \mathbf{a}_m] $$
If $\mathbf{E} = diag(e_1,\cdots,e_n)$, then:

$$
\mathbf{E} \mathbf{A} = 
\begin{bmatrix}
    e_1 \mathbf{a}_1^\top \\
    \vdots \\
    e_n \mathbf{a}_n^\top
\end{bmatrix}
$$

# Kronecker Product

The Kronecker product of an $m \times n$ matrix $Q$ and an $r \times s$ matrix P is an $mr \times ns$ matrix, $Q \otimes P$ defined as

$$
Q \otimes P = \begin{bmatrix}
  Q_{11} P & Q_{12} P & \cdots & Q_{1n} P \\
  Q_{21} P & Q_{22} P & \cdots & Q_{2n} P \\
  \vdots          & \vdots          & \ddots & \vdots          \\
  Q_{m1} P & Q_{q2} P & \cdots & Q_{mn} P
\end{bmatrix}
$$

Properties:
* $(A \otimes B)' = A' \otimes B'$

# Sources

[1] https://personal.math.ubc.ca/~yxli/matrices_in_rows_column_vectors.pdf