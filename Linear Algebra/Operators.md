# Tranpose

- The transpose of a matrix $\mathbf{A} \in \mathbb{R}^{n \times m}$, denoted $\mathbf{A}^T$, is obtained by interchanging rows and columns.

- If $\mathbf{A} = [a_{ij}]$, then $\mathbf{A}^T = [a_{ji}]$

- If $\mathbf{A} = [\mathbf{a}_1 | \cdots | \mathbf{a}_m]$, then
$$ \mathbf{A}^T = \begin{bmatrix} \mathbf{a}_1^\top \\ \vdots \\ \mathbf{a}_m^\top \end{bmatrix} $$

- If $\mathbf{A} = \begin{bmatrix} \mathbf{a}_1^\top \\ \vdots \\ \mathbf{a}_n^\top \end{bmatrix}$, then $\mathbf{A}^T = [\mathbf{a}_1 | \cdots | \mathbf{a}_n] $

# vec

$\text{vec}(\cdot)$ stacks the columns of a $n \times m$ matrix $Q$ into an  $nm \times 1$ vector.

Properties:
1. For any column vector $q$:  $$\text{vec}(q') = q$$

2. For conformable matrices $Q$ and $P$:  $$\text{vec}(Q+P) = \text{vec}(Q)+\text{vec}(P)$$

3. For matrices $Q$ and $P$ of dimensions $k \times l$ and $l \times m$:

$$\text{vec}(QP) = (I_m \otimes Q)\text{vec}(P) = (P' \otimes I_k)\text{vec}(Q)$$

4. Let $A$ be a $K	\times L$ matrix, $B$ an $L	\times M$ matrix and $r$ an $M \times 1$ vector, then:  $$ABr = (A \otimes r^T)vec(B^T)$$

Sources:
* Source for 4: https://www.statlect.com/matrix-algebra/vec-operator

# Inverse

* The inverse of a lower triangular matrix, if it exists, is also lower triangular.
