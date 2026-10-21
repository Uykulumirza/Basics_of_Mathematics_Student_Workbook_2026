# Solution to Exercise 11: Parameter and Invertibility

## 1. Problem Statement

Given the parameterized matrix:
$$A(t) = \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix}, \qquad t \in \mathbb{R}$$

1. Find all values of the parameter $t$ for which the matrix $A(t)$ is invertible.
2. Derive an explicit formula for the inverse matrix $A(t)^{-1}$ for all valid $t$.
3. Explain mathematically and geometrically what occurs in this formula and to the matrix at the excluded values of $t$.

---

## 2. Theoretical Background and Concepts

### Parameter-Dependent Invertibility
A matrix containing an algebraic parameter $t$ is invertible if and only if its determinant, viewed as a polynomial function in $t$, is non-zero:
$$\det A(t) \ne 0$$
The roots of the determinant equation $\det A(t) = 0$ define the set of singular (non-invertible) parameter values.

### The $2 \times 2$ Inverse Formula with a Parameter
When $\det A(t) \ne 0$:
$$A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} d(t) & -b(t) \\ -c(t) & a(t) \end{pmatrix}$$
At parameter values where $\det A(t) \to 0$:
- The entries of $A(t)^{-1}$ exhibit poles (vertical asymptotes), causing division by zero.
- Geometrically, the transformation loses one or more dimensions (the column/row vectors become collinear).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Determinant of $A(t)$
Compute the determinant using the standard $2 \times 2$ rule:
$$\det A(t) = (1)(1) - (t)(t) = 1 - t^2$$

Factoring the difference of squares:
$$\det A(t) = (1 - t)(1 + t)$$

---

### Step 2: Determine Invertibility Conditions
The matrix $A(t)$ is invertible if and only if:
$$\det A(t) \ne 0 \iff 1 - t^2 \ne 0 \iff t^2 \ne 1$$

Therefore:
$$t \ne 1 \qquad \text{and} \qquad t \ne -1$$

In interval notation, $A(t)$ is invertible for all:
$$t \in (-\infty, -1) \cup (-1, 1) \cup (1, \infty) = \mathbb{R} \setminus \{-1, 1\}$$

---

### Step 3: Derive the Inverse Formula for $A(t)^{-1}$
For any $t \ne \pm 1$, apply the explicit inversion formula:
$$A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix}$$

Writing out the individual rational entries:
$$A(t)^{-1} = \begin{pmatrix} \frac{1}{1 - t^2} & \frac{-t}{1 - t^2} \\ \frac{-t}{1 - t^2} & \frac{1}{1 - t^2} \end{pmatrix}$$

---

### Step 4: Analysis of Excluded Values ($t = 1$ and $t = -1$)

1. **Case $t = 1$:**
   - Substituting $t = 1$ into $A(t)$ gives:
     $$A(1) = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$$
   - **Row/Column Collapse:** The two rows (and columns) are identical: $R_1 = R_2 = (1, 1)$.
   - **Algebraic Effect:** The determinant vanishes ($\det A(1) = 0$). In the inverse formula, the denominator becomes $1 - (1)^2 = 0$, resulting in division by zero.
   - **Geometric Effect (Mapping vs. Projection):** For any vector $x = (x_1, x_2)^T$, $A(1)x = (x_1 + x_2, x_1 + x_2)^T$, so $A(1)$ maps all of $\mathbb{R}^2$ onto the 1D diagonal line $y = x$. However, $A(1)$ is **not itself a projection** onto $y = x$, because a true projection $P$ must be idempotent ($P^2 = P$, fixing every point already on the target line), whereas:
     $$A(1)^2 = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & 2 \\ 2 & 2 \end{pmatrix} = 2A(1)$$
     Since the orthogonal projection onto $y = x$ is $P_+ = \frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$, the matrix $A(1) = 2P_+$ equals **twice the orthogonal projection** onto $y = x$ (it projects orthogonally onto $y = x$ and then scales along that line by a factor of $2$). Meanwhile, the entire orthogonal line $x_1 + x_2 = 0$ ($y = -x$) is collapsed to the origin ($\ker A(1) = \operatorname{span}\{(-1, 1)^T\}$), destroying information and making inversion impossible.

2. **Case $t = -1$:**
   - Substituting $t = -1$ into $A(t)$ gives:
     $$A(-1) = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$$
   - **Row/Column Collapse:** The rows are exact opposites: $R_2 = -R_1$.
   - **Algebraic Effect:** The determinant is $\det A(-1) = 1 - (-1)^2 = 0$, again causing undefined division by zero in the inverse formula.
   - **Geometric Effect (Mapping vs. Projection):** For any $x = (x_1, x_2)^T$, $A(-1)x = (x_1 - x_2, -(x_1 - x_2))^T$, so $A(-1)$ maps $\mathbb{R}^2$ onto the line $y = -x$. Just as before, $A(-1)$ is not a projection because:
     $$A(-1)^2 = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & -2 \\ -2 & 2 \end{pmatrix} = 2A(-1)$$
     Instead, $A(-1) = 2P_-$ equals **twice the orthogonal projection** $P_- = \frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$ onto the line $y = -x$, while collapsing the orthogonal line $y = x$ into the origin ($\ker A(-1) = \operatorname{span}\{(1, 1)^T\}$).

3. **Asymptotic Behavior as $t \to \pm 1$:**
   $$\lim_{t \to 1} \|A(t)^{-1}\| = \infty, \qquad \lim_{t \to -1} \|A(t)^{-1}\| = \infty$$
   As $t$ approaches either critical value, the entries of the inverse matrix grow without bound.

---

## 4. Verification and Consistency Checks

1. **Product Verification for Arbitrary $t \ne \pm 1$:**
   $$A(t) A(t)^{-1} = \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix} \cdot \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix} = \frac{1}{1 - t^2} \begin{pmatrix} 1(1) + t(-t) & 1(-t) + t(1) \\ t(1) + 1(-t) & t(-t) + 1(1) \end{pmatrix}$$
   $$= \frac{1}{1 - t^2} \begin{pmatrix} 1 - t^2 & 0 \\ 0 & 1 - t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

2. **Specific Value Check ($t = 0$):**
   At $t = 0$, $A(0) = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$.
   Using the formula:
   $$A(0)^{-1} = \frac{1}{1 - 0^2} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

3. **Specific Value Check ($t = 2$):**
   At $t = 2$, $A(2) = \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix}$. $\det A(2) = 1 - 4 = -3$.
   $$A(2)^{-1} = \frac{1}{-3} \begin{pmatrix} 1 & -2 \\ -2 & 1 \end{pmatrix} = \begin{pmatrix} -1/3 & 2/3 \\ 2/3 & -1/3 \end{pmatrix}$$
   Check product:
   $$\begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} -1/3 & 2/3 \\ 2/3 & -1/3 \end{pmatrix} = \begin{pmatrix} -1/3 + 4/3 & 2/3 - 2/3 \\ -2/3 + 2/3 & 4/3 - 1/3 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$
