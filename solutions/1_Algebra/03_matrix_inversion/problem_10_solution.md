# Solution to Exercise 10: Inverse of a Diagonal Matrix

## 1. Problem Statement

Given the diagonal matrices:
$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix}, \qquad E = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 5 \end{pmatrix}$$

1. Without using Gauss–Jordan elimination, determine which of the two matrices is invertible.
2. For the invertible matrix, provide its inverse matrix directly.
3. Verify the result by explicit matrix multiplication.

---

## 2. Theoretical Background and Concepts

### Invertibility and Inverses of Diagonal Matrices
A square matrix $M = \operatorname{diag}(d_1, d_2, \dots, d_n)$ is diagonal if all off-diagonal entries are zero ($m_{ij} = 0$ for $i \ne j$).

1. **Determinant of a Diagonal Matrix:**
   The determinant of a diagonal matrix is simply the product of its diagonal entries:
   $$\det M = \prod_{i=1}^n d_i = d_1 \cdot d_2 \cdots d_n$$
2. **Invertibility Criterion:**
   $M$ is invertible if and only if $\det M \ne 0$, which holds if and only if:
   $$d_i \ne 0 \quad \text{for all } i \in \{1, 2, \dots, n\}$$
   If even a single diagonal entry is zero ($d_k = 0$), the entire $k$-th row is zero, making $\operatorname{rank}(M) < n$ and rendering $M$ singular.
3. **Explicit Inverse Formula:**
   When all $d_i \ne 0$, the inverse of a diagonal matrix is also diagonal, with each diagonal entry replaced by its reciprocal:
   $$M^{-1} = \operatorname{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right) = \begin{pmatrix} 1/d_1 & 0 & \cdots & 0 \\ 0 & 1/d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1/d_n \end{pmatrix}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analyze Invertibility of Matrix $D$
Examine the diagonal entries of $D$:
$$d_{11} = 2 \ne 0, \qquad d_{22} = -3 \ne 0, \qquad d_{33} = 5 \ne 0$$

- All diagonal entries are strictly non-zero.
- The determinant is:
  $$\det D = (2)(-3)(5) = -30 \ne 0$$
- Therefore, matrix $D$ is **invertible**.

---

### Step 2: Analyze Invertibility of Matrix $E$
Examine the diagonal entries of $E$:
$$e_{11} = 2, \qquad e_{22} = 0, \qquad e_{33} = 5$$

- The second diagonal entry is zero ($e_{22} = 0$).
- Consequently, the entire second row is a row of zeros:
  $$\text{Row}_2(E) = (0, 0, 0)$$
- The determinant is:
  $$\det E = (2)(0)(5) = 0$$
- Any vector $v = (0, 1, 0)^T$ maps to the zero vector: $Ev = 0$. The kernel is non-trivial, so $\operatorname{rank}(E) \le 2 < 3$.
- Therefore, matrix $E$ is **singular (not invertible)**.

---

### Step 3: Determine the Inverse Matrix $D^{-1}$
For the invertible matrix $D$, take the reciprocal of each non-zero diagonal entry:
$$D^{-1} = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & \frac{1}{-3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix}$$

---

### Step 4: Verification via Matrix Multiplication
Compute the product $D D^{-1}$:
$$D D^{-1} = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix}$$

Evaluate entry by entry:
- Entry $(1, 1)$: $2 \cdot \frac{1}{2} = 1$
- Entry $(2, 2)$: $(-3) \cdot \left(-\frac{1}{3}\right) = 1$
- Entry $(3, 3)$: $5 \cdot \frac{1}{5} = 1$
- All off-diagonal entries are sums of products involving zeros, hence $0$.

Thus:
$$D D^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3 \quad \checkmark$$

Similarly:
$$D^{-1} D = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix} \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3 \quad \checkmark$$

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicative Consistency:**
   $$\det(D^{-1}) = \left(\frac{1}{2}\right)\left(-\frac{1}{3}\right)\left(\frac{1}{5}\right) = -\frac{1}{30}$$
   Comparing with $\det D = -30$:
   $$\det(D) \cdot \det(D^{-1}) = (-30)\left(-\frac{1}{30}\right) = 1 = \det(I_3) \quad \checkmark$$

2. **Structural Check on $E$:**
   If an inverse $E^{-1} = [x_{ij}]$ existed, then entry $(2, 2)$ of the product $E E^{-1}$ would be:
   $$\text{Row}_2(E) \cdot \text{Col}_2(E^{-1}) = 0 \cdot x_{12} + 0 \cdot x_{22} + 0 \cdot x_{32} = 0$$
   However, for $E E^{-1} = I_3$, this entry must equal $1$. Since $0 \ne 1$, no matrix $E^{-1}$ can ever satisfy $E E^{-1} = I_3$.
