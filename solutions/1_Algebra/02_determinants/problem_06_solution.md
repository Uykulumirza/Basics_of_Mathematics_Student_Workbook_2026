# Solution to Exercise 6: Parameter and Invertibility

## 1. Problem Statement

Given the parameter-dependent family of matrices:
$$A(t) = \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix}, \qquad t \in \mathbb{R}$$

1. Find all values of the real parameter $t$ for which the matrix $A(t)$ is not invertible.
2. Explain in detail how this non-invertibility is fundamentally related to the determinant being equal to zero.

---

## 2. Theoretical Background and Concepts

### Invertibility and the Determinant
For any square matrix $M \in M_n(\mathbb{R})$, the following statements are logically equivalent:
1. $M$ is invertible (there exists $M^{-1}$ such that $M M^{-1} = M^{-1} M = I$).
2. $\det M \ne 0$.
3. The column (and row) vectors of $M$ are linearly independent.
4. The null space is trivial: $\ker(M) = \{0\}$.
5. The rank of $M$ is maximal: $\operatorname{rank}(M) = n$.

Conversely:
$$M \text{ is not invertible (singular)} \iff \det M = 0$$

### Geometric and Algebraic Interpretation of $\det M = 0$
- **Algebraically:** A zero determinant indicates that at least one eigenvalue is zero, which implies the existence of a non-zero vector $v \ne 0$ such that $Mv = 0$. Since distinct vectors are collapsed to the same output (non-injective), the map has no inverse.
- **Geometrically:** The determinant measures the oriented area distortion. When $\det M = 0$, the transformation collapses the 2D plane onto a 1D line (or a single point), losing information irrecoverably.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Determinant $\det A(t)$
Using the $2 \times 2$ determinant formula:
$$\det A(t) = \begin{vmatrix} t & 1 \\ 2 & t \end{vmatrix} = (t)(t) - (1)(2) = t^2 - 2$$

---

### Step 2: Solve the Singular Condition $\det A(t) = 0$
Matrix $A(t)$ fails to be invertible precisely when its determinant vanishes:
$$t^2 - 2 = 0 \implies t^2 = 2$$

Taking the square root of both sides gives two solutions:
$$t = \sqrt{2} \qquad \text{or} \qquad t = -\sqrt{2}$$

Thus, the matrix is not invertible for:
$$t \in \{-\sqrt{2}, \; \sqrt{2}\}$$

---

### Step 3: Explanation of the Connection Between $\det A(t) = 0$ and Non-Invertibility

1. **Case $t = \sqrt{2}$:**
   $$A(\sqrt{2}) = \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix}$$
   Notice that row 2 is a scalar multiple of row 1:
   $$R_2 = \begin{pmatrix} 2 & \sqrt{2} \end{pmatrix} = \sqrt{2} \begin{pmatrix} \sqrt{2} & 1 \end{pmatrix} = \sqrt{2} R_1$$
   Because the rows are linearly dependent, the matrix has rank $1 < 2$. The kernel contains non-trivial solutions:
   $$\begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix} \begin{pmatrix} 1 \\ -\sqrt{2} \end{pmatrix} = \begin{pmatrix} \sqrt{2} - \sqrt{2} \\ 2 - 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
   Since non-zero vectors map to the zero vector, $A(\sqrt{2})$ is not injective and cannot have an inverse.

2. **Case $t = -\sqrt{2}$:**
   $$A(-\sqrt{2}) = \begin{pmatrix} -\sqrt{2} & 1 \\ 2 & -\sqrt{2} \end{pmatrix}$$
   Here, row 2 is also a scalar multiple of row 1:
   $$R_2 = -\sqrt{2} R_1$$
   Similarly, non-trivial vectors lie in the null space:
   $$\begin{pmatrix} -\sqrt{2} & 1 \\ 2 & -\sqrt{2} \end{pmatrix} \begin{pmatrix} 1 \\ \sqrt{2} \end{pmatrix} = \begin{pmatrix} -\sqrt{2} + \sqrt{2} \\ 2 - 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
   The mapping is singular and irreversible.

---

## 4. Verification and Consistency Checks

1. **Formula Check for General Invertible $t$:**
   For any $t \notin \{-\sqrt{2}, \sqrt{2}\}$, the determinant $t^2 - 2 \ne 0$, and the explicit inverse is:
   $$A(t)^{-1} = \frac{1}{t^2 - 2} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix}$$
   Checking the product:
   $$A(t) A(t)^{-1} = \frac{1}{t^2 - 2} \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix} = \frac{1}{t^2 - 2} \begin{pmatrix} t^2 - 2 & -t + t \\ 2t - 2t & -2 + t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$$
   This formula is valid for all $t$ except where the denominator $t^2 - 2 = 0$, directly confirming that division by zero (and hence non-existence of the inverse) occurs if and only if $t = \pm\sqrt{2}$.

2. **Test Point ($t = 0$):**
   $$\det A(0) = 0^2 - 2 = -2 \ne 0 \implies A(0) = \begin{pmatrix} 0 & 1 \\ 2 & 0 \end{pmatrix} \text{ is invertible, with } A(0)^{-1} = \begin{pmatrix} 0 & 1/2 \\ 1 & 0 \end{pmatrix} \quad \checkmark$$
