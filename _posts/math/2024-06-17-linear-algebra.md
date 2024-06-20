---
layout: post
title: "Notes on Linear Algebra"
---

Linear algebra is the study of vectors and matrices.

<br>

## 1. Vectors

A vector $\boldsymbol{x} \in \mathcal{R}^n$ is a $n$-tuple of real numbers.

$$ \begin{equation} \boldsymbol{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} \end{equation} $$

The operations we can perform on vectors are addition, subtraction, scaling, dot product, cross product, outer product, norm and projection.

### **Dot product / inner product**
takes in two vectors as inputs and produces a single number: $. : \mathcal{R}^n \times \mathcal{R}^n \rightarrow \mathcal{R}$. It is computed as $\boldsymbol{x}.\boldsymbol{y} = \boldsymbol{x}^T\boldsymbol{y} = \sum\_{i=1}^n x\_i y\_i = ||\boldsymbol{x}||\_2 ||\boldsymbol{y}||\_2 \cos{\theta}$ where $||.||\_2$ denotes the L$2$ norm of the vector, and $\theta$ is the angle between the two vectors. The dot product is used for calculating vector projections, vector decompositions, and determining orthogonality.
    
### **Cross product / vector product**
takes in two vectors as inputs and produces another vector: $\times : \mathcal{R}^n \times \mathcal{R}^n \rightarrow \mathcal{R}^n$. Computing the cross product requires a specific combination of multiplications and subtractions of the input vectors’ components. It is equivalent to $\boldsymbol{x} \times \boldsymbol{y} = ||\boldsymbol{x}||_2 \: ||\boldsymbol{y}||_2 \sin{\theta} \: \boldsymbol{n}$, where $\boldsymbol{n}$ is an unit vector perpendicular to the plane containing the two input vectors. Thus, the cross product is useful for determining the normal vector to a surface. Also, due to the presence of the $\sin$ term, the cross-product is $0$ if the two input vectors are parallel.
    
### **Outer product**
takes in two vectors as inputs and produces a matrix: $\otimes: \mathcal{R}^m \times \mathcal{R}^n \rightarrow \mathcal{R}^{m \times n}$. It is computed as $\boldsymbol{x} \otimes\boldsymbol{y} = \boldsymbol{x}\boldsymbol{y}^T$, and is useful for producing rank $1$ matrices.
    
### The **norm** of a vector
is a non-negative number that indicates the size of the vector. A particular norm is the euclidean norm a.k.a the L$2$ norm: $||\boldsymbol{x}||\_2 = \sqrt{\sum\_{i=1}^n x\_i^2}$.
    
### **Projection** of a vector
$\boldsymbol{x}$ onto another vector $\boldsymbol{d}$ is given by $\boldsymbol{x}.\boldsymbol{d}\frac{\boldsymbol{d}}{||\boldsymbol{d}||\_2}$, where $\frac{\boldsymbol{d}}{||\boldsymbol{d}||\_2}$ gives an unit vector in the direction of $\boldsymbol{d}$.

<br>
 
## 2. Matrices

A matrix $A \in \mathcal{R}^{m \times n}$ is a rectangular array of numbers with $m$ rows and $n$ columns.

$$ \begin{equation} A =
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\end{equation} $$

The operations we can perform on matrices are addition, subtraction, scaling by a scalar, matrix-vector product, matrix-matrix product, matrix inverse, trace and determinant.

 - **Matrix-matrix multiplication**: If $A \in \mathcal{R}^{m \times n}$ and $B \in \mathcal{R}^{n \times p}$, then $C = AB \in \mathcal{R}^{m \times p}$ is such that each column of $C$, $\boldsymbol{c_j}$ is the matrix-vector product $A \boldsymbol{b_j}$. Matrix multiplication is so defined so as to enable us to compose linear transformations, that is, $A(B\boldsymbol{x}) = (AB)\boldsymbol{x} = C\boldsymbol{x}$. This also shows that the composition of two linear transformations is also a linear transformation.
    
 - The **Determinant** operator maps square matrices to real numbers: $\text{det}(A): \mathcal{R}^{n \times n} \rightarrow \mathcal{R}$. The determinant of the matrix $A_T$ is the scale factor associated with the linear transformation $T$. The sign of the determinant tells us information about the relative orientation of the vectors before and after the transformation. For square matrices of the same size $A$ and $B$:

     - $\text{det}(AB) = \text{det}(A)\text{det}(B) = \text{det}(BA)$.
     - If $\text{det}(A) \neq 0$, $A$ is invertible and $\text{det}(A^{-1}) = 1 / \text{det}(A)$. 
     - If $\text{det}(A) = 0$, the columns of $A$ are linearly dependent, and A is non-invertible.
     - If $\text{det}(A) = 1$, the transformation is volume-preserving.
     - $\text{det}(\alpha A) = \alpha^n \text{det}(A)$ if $A \in \mathcal{R}^{n \times n}$.
     - $\text{det}(A) = \prod_{i=1}^n \lambda_i$, where $\lambda_i$ are the eigenvalues of $A$.

<br>

## 3. Matrix-vector products compute linear transformations

The product of a matrix $A \in \mathcal{R}^{m \times n}$ with a vector $\boldsymbol{x} \in \mathcal{R}^n$ produces another vector that is a linear combination of the columns of $A$ with the coefficients of the linear combination given by the elements of $x$.

$$ \begin{equation} \boldsymbol{y} =
\begin{bmatrix}
| & | & & | \\
\boldsymbol{a_1} & \boldsymbol{a_2} & \cdots & \boldsymbol{a_n} \\
| & | & & |
\end{bmatrix}
\begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix} =
\sum_{i=1}^n  x_i \boldsymbol{a_i}
\label{eqn_linear}
\end{equation}$$

Matrix-vector products play an important role in linear algebra because of their relation to linear transformations. Specifically, multiplication with a matrix computes a linear transformation $T_A: \mathcal{R}^n \rightarrow \mathcal{R}^m$ that takes $n$-vectors as inputs and produces $m$-vectors as outputs. Instead of writing $\boldsymbol{y} = T_A(\boldsymbol{x})$, we write $\boldsymbol{y} = A\boldsymbol{x}$, and say that $T_A$ is represented by the matrix $A$.

The transformation $T_A$ is linear. That is, it satisfies the property: $T_A (\sum_{i=1}^n \alpha_i \boldsymbol{x_i}) = \sum_{i=1}^n T_A \boldsymbol{x_i}$.

For every linear transformation $T$, there exists a matrix $A_T$ such that $T$ can be computed as a matrix-vector product $A_T \boldsymbol{x}$. Equivalently, every matrix $A \in \mathcal{R}^{m \times n}$ corresponds to some linear transformation $T_A: \mathcal{R}^n \rightarrow \mathcal{R}^m$.

<br>

### Geometric implications of linearity
To understand the geometric implications of this linearity, consider the case where $m = n = 2$. Here, both vectors $\boldsymbol{x}$ and $\boldsymbol{y}$ belong to $\mathcal{R}^2$. The function $A$ maps each vector in the input space to a corresponding vector in the output space. We can visualize each vector in the input space as a point defined by its coordinates.

Now, think about the input and output grids. Geometrically, linearity means that grid lines that are parallel and evenly spaced in the input grid will remain parallel and evenly spaced in the output grid. However, the angles between perpendicular grid lines may change. See [Grant Sanderson's blog](https://www.3blue1brown.com/lessons/linear-transformations) for nice visualizations.

<br>

### Columns of $A_T$ are [images](https://en.wikipedia.org/wiki/Image_%28mathematics%29) of the basis vectors of the input vector space
To find the matrix corresponding to a linear transformation $T$, it is sufficient to know the [images](https://en.wikipedia.org/wiki/Image_%28mathematics%29) of the standard basis vectors of the input space under $T$. From Eqn. \ref{eqn_linear}, we can deduce that:

$$ \begin{equation}
\begin{bmatrix} | \\ \boldsymbol{a_i} \\ | \end{bmatrix} =
\begin{bmatrix}
| & | & & | \\
\boldsymbol{a_1} & \boldsymbol{a_2} & \cdots & \boldsymbol{a_n} \\
| & | & & |
\end{bmatrix}
\begin{bmatrix} | \\ \boldsymbol{e_i} \\ | \end{bmatrix} =
\begin{bmatrix} | \\ T \boldsymbol{e_i} \\ | \end{bmatrix}
\label{eqn_linear2}
\end{equation}$$


$$ \begin{equation} A_T =
\begin{bmatrix}
| & | & & | \\
T \boldsymbol{e_1} & T \boldsymbol{e_2} & \cdots & T \boldsymbol{e_n} \\
| & | & & |
\end{bmatrix}
\label{eqn_linear3}
\end{equation}$$

Eqn. \ref{eqn_linear3} allows us to readily specify matrices for certain simple transformations. For instance, in order to rotate $2$d space counter-clockwise by 90 degrees, the first basis vector $[1 \hspace{5pt} 0] ^ {\text{T}}$ should be mapped to $[0 \hspace{5pt} 1] ^ {\text{T}}$, and the second basis vector $[0 \hspace{5pt} 1] ^ {\text{T}}$ should be mapped to $[-1 \hspace{5pt} 0] ^ {\text{T}}$. Thus, the matrix representing this transformation is
$\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$.
Similarly, the matrix that represents isotropic scaling by a factor of $2$ is
$\begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}$.

 
<br>

## 4. Matrix inverse

A matrix represents a linear transformation from an input vector space to an output vector space. If this transformation is invertible, the inverse transformation is represented by the inverse of the matrix. Only square matrices can have an inverse. A matrix $A\in \mathcal{R}^{n \times n}$ is invertible if and only if $\text{det}(A) \neq 0$. The following statements are true for invertible matrices: all their $n$ columns are linearly independent, they have full rank, and none of their eigenvalues are $0$. 

Non-invertible matrices are known as **singular** matrices. The term singular means exceptional or unusual. Singular matrices are considered unusual, as randomly generated square matrices will almost never be singular (have a zero determinant). Singular matrices are an infinitely thin subset in the space of all square matrices. Any tiny perturbation to a singular matrix is almost certain to make it non-singular (invertible). See [this blog](https://www.johndcook.com/blog/2012/06/13/matrix-condition-number/) for a discussion on converting singular matrices to invertible ones.

A related concept is that of the **condition number** of a matrix, which indicates the degree of singularity of the matrix. That is, the larger the condition number of a matrix, the more difficult it is to invert (the matrix inversion procedure is more susceptible to instability caused by numerical computation errors).
 
<br>

## 5. Changing Bases

Eqn. \ref{eqn_linear3} highlights the fact that the same linear transformation T can be represented by a different matrix by choosing a different basis of the input or the output vector space. Unless specified otherwise, we generally assume the use of the standard bases. That said, let's talk a little about how do representations of vectors and matrices change when the basis is changed. This notion will also directly lead us to the idea of eigendecomposition, where we search for a basis such that the transformation with respect to that basis has a nicer representation.

### Basis
A set of vectors $\{\boldsymbol{v_1}, \boldsymbol{v_2}, \cdots \boldsymbol{v_n}\}$ is known to be a basis of a vector space $\mathcal{V}$ if it linearly independent and it spans $\mathcal{V}$. The standard basis of $\mathcal{R}^n$ (used above in Eqn. \ref{eqn_linear2} and Eqn. \ref{eqn_linear3}) is denoted by $\{\boldsymbol{e_1}, \boldsymbol{e_2}, \cdots \boldsymbol{e_n}\}$ where $\boldsymbol{e_i} \in \mathcal{R}^n$ is a one-hot vector with its $i^{th}$ component equal to $1$.

### Representation of a vector under a new basis
Note that implicit in the representation of a vector $\boldsymbol{x} \in \mathcal{R}^3$ as $\boldsymbol{x}= [x_1, x_2, x_3]$ is the choice of the standard basis $\{\boldsymbol{e_1}, \boldsymbol{e_2}, \boldsymbol{e_3}\}$. The same vector can be represented as $\boldsymbol{x}= [\hat{x}_1, \hat{x}_2, \hat{x}_3]$ in another basis $\{\boldsymbol{\hat{e}_1}, \boldsymbol{\hat{e}_2}, \boldsymbol{\hat{e}_3}\}$ using the change-of-basis matrix whose columns describe the vectors of the old basis ${\boldsymbol{e_i}}$ in terms of the new basis ${\boldsymbol{\hat{e}_i}}$.

$$ \begin{equation}
\begin{bmatrix} \hat{x}_1 \\ \hat{x}_2 \\ \hat{x}_3 \end{bmatrix} =
\begin{bmatrix}
\boldsymbol{\hat{e}_1}.\boldsymbol{e_1} &
\boldsymbol{\hat{e}_1}.\boldsymbol{e_2} &
\boldsymbol{\hat{e}_1}.\boldsymbol{e_3} \\
\boldsymbol{\hat{e}_2}.\boldsymbol{e_1} &
\boldsymbol{\hat{e}_2}.\boldsymbol{e_2} &
\boldsymbol{\hat{e}_2}.\boldsymbol{e_3} \\
\boldsymbol{\hat{e}_3}.\boldsymbol{e_1} & 
\boldsymbol{\hat{e}_3}.\boldsymbol{e_2} & 
\boldsymbol{\hat{e}_3}.\boldsymbol{e_3}
\end{bmatrix}
\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} \end{equation}$$

### Representation of a matrix under a new basis
Given a matrix $N \in \mathcal{R}^{n \times n}$ representing a linear transformation in a certain basis, and an invertible matrix $P \in \mathcal{R}^{n \times n}$ whose columns form a new basis, then $M = P N P^{-1}$ represents the same linear transformation under the new basis. $M$ and $N$ are said to be related by a similarity transformation. As $M$ and $N$ represent the same linear transformation, they share the same determinant, trace, rank and eigenvalues. 

<br>

## 6. Eigen Decomposition

As noted above, the same linear transformation can be represented by different matrices depending on the choice of basis in the input and output spaces. Given such a choice, the columns of the matrix are images of the input basis vectors under the transformation, expressed in terms of the output basis vectors.

Eigenvectors of a matrix are special input vectors which undergo simple scaling under the linear transformation described by the matrix. If $n$ such eigenvectors exist for a transformation from $\mathcal{R}^n$ to $\mathcal{R}^n$, the representation of the matrix will be diagonal under a basis defined by the set of eigenvectors.

Such a basis is said to be "natural basis" for the matrix. Each matrix has its own (in German, eigene) natural basis. Therefore, the vectors forming the basis are called as the eigenvectors of the matrix. The corresponding scaling factors are known as the eigenvalues. The eigendecomposition is a change-of-basis operation that expresses a matrix $A$ with respect to its eigenbasis:

$$ \begin{equation} A = Q \Lambda Q^{-1} \label{eqn_eigen} \end{equation}$$ 

The matrices $A$ and $\Lambda$ are similar matrices, with $A$ represented in the standard basis and $\Lambda$ represented in the eigenbasis. $\Lambda$ is a diagonal matrix, with its diagonal entries being the eigenvalues of $A$.

Finding eigenvalues and eigenvectors of $A$: Given $A$, its eigenvalues can be determined as the roots of its characteristic polynomial $\text{det}(A - \lambda I) = 0$. Then, we can find the eigenvectors corresponding to the eigenvalue $\lambda_i$ by computing the null space of the matrix $A - \lambda_i I$, that is, by finding vectors $\boldsymbol{e}\_{\lambda\_i}$ that the matrix $A - \lambda\_i I$ maps to the zero vector, that is, by solving the system of equations $(A - \lambda\_i I) \boldsymbol{e}\_{\lambda\_i} = \boldsymbol(0)$.

### Existence of eigendecomposition
As rectangular matrices map vectors between two spaces of differing dimensions, they cannot simply scale an input vector. Thus, the eigendecomposition is not applicable to such matrices. Even for square matrices, some of them have repeated eigenvalues, and the number of eigenvectors is less than the dimensionality of the vector space. Such square matrices do not have an eigendecomposition. If a $n \times n$ square matrix that has $n$ eigenvectors, it is said to be diagonalizable, and its eigendecomposition is given by Eqn. \ref{eqn_eigen}.

<br>

## 7. Special Matrices

### Diagonal Matrices
The eigenvalues of a diagonal matrix $A$ are $\lambda_i = a_{ii}$.

### Symmetric Matrices
$A$ is symmetric is $A^T = A$. For any matrix $B \in \mathcal{R}^{n \times m}$, the matrices $BB^T$ and $B^TB$ are symmetric. Eigenvalues of symmetric matrices are real, and eigenvectors are orthonormal. Symmetric matrices with complex numbers are called Hermitian matrices.

### Orthogonal Matrices
$O$ is an orthogonal matrix if its columns are mutually orthonormal. That is, $OO^T = O^TO = I$. In other words, $O^{-1} = O^T$. The eigenvalues of orthogonal matrices are all $1$ is they are real, and have unit length if they are complex. The determinant of orthogonal matrices is $1$ or $-1$. The set of orthogonal matrices contains three special cases: rotations matrices, reflection matrices, and permutation matrices. Orthogonal matrices with complex numbers are called unitary matrices.

### Positive Semi-Definite Matrices
A matrix $P \in \mathcal{R}^{n \times n}$ is positive semi-definite if $\boldsymbol{x}^TA\boldsymbol{x} \geq 0 \: \forall \: \boldsymbol{x} \in \mathcal{R}^{n}$. All eigenvalues of such matrices are non-negative.

| Matrix    | Eigen-values   | Eigen-vectors   |
|-----------|----------------| ----------------|
| Diagonal | $\lambda_i = a_{ii}$ | $\boldsymbol{v_i} = \boldsymbol{e_i}$|
| Symmetric | Real | Orthonormal|
| Orthogonal | $1$ (if real) / unit norm (if complex)| |
| Positive Semi-Definite | Non-negative | |

<br>

## 8. Singular Value Decomposition
The SVD generalizes the notion of eigenvalues and eigenvectors to non-square matrices. Any non-square matrix $A \in \mathcal{R}^{m \times n}$ can be decomposed as follows, where $U \in \mathcal{R}^{m \times m}$ and $V \in \mathcal{R}^{n \times n}$ are orthogonal matrices and $\Sigma \in \mathcal{R}^{m \times n}$ is a diagonal matrix. Geometrically, the orthogonal matrices $U$ and $V$ represent rotations and the diagonal matrix $\Sigma$ represents scaling.

$$ \begin{equation} A = U \Sigma V^{T} \end{equation} $$ 

[This](https://gregorygundersen.com/blog/2018/12/10/svd/) is an excellent blog post to build intuition about the SVD beyond the mere statement of its existence that we provided here. Further, [this](https://jeremykun.wordpress.com/2016/04/18/singular-value-decomposition-part-1-perspectives-on-linear-algebra/) blog post is a nice take on what it means to do SVD of a data matrix.

<br>

## 9. Applications of Linear Algebra

### 9.1 Graphs
A graph is defined as pair of sets $G = (V, E)$, where $V$ is the set of vertices and $E$ is the set of edges in the graph $G$. A graph with $n$ vertices can also be represented by a $n \times n$ adjacency matrix $A$ where $a_{ij} = 1$ if an edge exists between vertices $i$ and $j$, and $0$ otherwise. Amazingly, doing matrix algebra on $A$ can help us answer questions about connectivity of the graph. For instance, the number of ways to go from $i$ to $j$ in exactly $m$ steps is given by $A^m (i,j)$.

### 9.2 Least square approximate solutions
An equation of the form
$A\boldsymbol{x} = \boldsymbol{y}$
could have exactly one solution (if $A$ is invertible), infinitely many solutions (if $A$ has a null space), or no solution at all
(if $\boldsymbol{y}$ is not in the column space of $A$).
In the third case, it is of interest to find an approximate solution
$\boldsymbol{x}^\*$
such that the vector
$A\boldsymbol{x}^\*$
is as close as possible to
$\boldsymbol{y}$.
This solution is given by $\boldsymbol{x}^\* = (A^TA)^{-1}A^T\boldsymbol{y}$, where $(A^TA)^{-1}$ is known as the **Moore–Penrose pseudoinverse** of $A$.

### 9.3 Computer graphics
Some geometric transformations such as scalings, rotations, reflections, and orthogonal projections can be represented as matrix-vector products. In order to represent translations and perspective projections via matrix-vector products too, we introduce homogeneous coordinates. A vector $\boldsymbol{x} = (x_1, x_2, x_3) \in \mathcal{R}^3$ corresponds to $\boldsymbol{X} = (x_1, x_2, x_3, 1) \in \mathcal{R}^4$ in homogeneous coordinates.

### 9.4 Markov chains
A random process is a model of a system that undergoes transitions between states over time. The state of the system at time $t+1$, denoted by $X_{t+1}$, depends on the previous states. This relationship can be encoded in the transition probability distribution, $p_{X_{t+1}|X_t, X_{t-1},\cdots X_0}(x_{t+1}|x_t, x_{t-1},\cdots x_0)$. In a markov process or a markov chain, this transition probability depends only on the previous state. Thus, $p_{X_{t+1}|X_t, X_{t-1},\cdots X_0}(x_{t+1}|x_t, x_{t-1},\cdots x_0)$ = $p_{X_{t+1}|X_t}(x_{t+1}|x_t)$.

If the state of the system can take on $n$ discrete values, the transition probability $p_{X_{t+1}\|X_t}(x_{t+1}\|x_t)$ can be represented by a $n \times n$ matrix, $M$. Given an initial state $X_0$, we can obtain the distribution over the possible states at $t=1$ by computing the matrix product $MX_0$. Similarly, the distribution over the possible states at $t=2$ would be $MMX_0$, and so on.

If the evolution of a Markov chain continues for long enough, the probability vector will converge to a stable distribution vector that remains unchanged when multiplied by $M$. This would be the eigenvector of $M$ with eigenvalue of $1$.

<br>

## 10. Details

 - **Linear v/s affine functions**: Linear functions ($\boldsymbol{y} = A \boldsymbol{x}$) are lines or planes that pass through the origin, while affine functions ($\boldsymbol{y} = A \boldsymbol{x} + \boldsymbol{b}$) are lines or planes that may be shifted.
 - Matrices have two interpretations. One, they represent linear transformations between vector spaces. Two, they serve as tabular placeholders for data. It is important to recognize which application is using matrices in which interpretation. [This](https://gregorygundersen.com/blog/2022/08/28/matrices-as-functions-and-data/) blog post and [this](https://www.jeremykun.com/2016/04/18/singular-value-decomposition-part-1-perspectives-on-linear-algebra/) blog post shed further light on these two interpretations of matrices.
 - While both linear algebra and $\sigma$-algebra share the term "algebra," they are unrelated in their definitions and applications. Linear algebra focuses on vectors and matrices and has applications in physics, engineering and computer science, while σ-algebra focuses on sets and measures, and is primarily used in probability theory, statistics, and real analysis.

<br>

## References
 - No bullshit guide to linear algebra, Ivan Savov. [link](https://minireference.com/static/excerpts/noBSLA_v2_preview.pdf)
 - Zico Kolter's linear algebra review [link](https://www.cs.cmu.edu/~zkolter/course/linalg/linalg_notes.pdf)
 - Grogory Gundersen's blog on SVD [link](https://gregorygundersen.com/blog/2018/12/10/svd/)