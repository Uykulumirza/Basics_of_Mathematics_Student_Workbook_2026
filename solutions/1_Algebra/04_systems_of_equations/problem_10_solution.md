# Exercise 10: A Polynomial Through Three Points

## 1. Problem Statement
Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

---

## 2. Theoretical Background and Concepts
A point $(x_0, y_0)$ lies on the graph of a polynomial $p(x) = ax^2 + bx + c$ if and only if evaluating the polynomial at $x = x_0$ gives $p(x_0) = y_0$:
$$a x_0^2 + b x_0 + c = y_0.$$
Although $p(x)$ is quadratic in the independent variable $x$, the interpolation condition $a x_0^2 + b x_0 + c = y_0$ is **linear in the unknown coefficients $(a, b, c)$** once $x_0$ and $y_0$ are fixed numbers. Imposing this condition at three points with distinct $x$-coordinates $(x_1, y_1), (x_2, y_2), (x_3, y_3)$ produces a $3\times 3$ linear system (with a Vandermonde coefficient matrix) that uniquely determines $(a, b, c)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Substitute the three points to set up the linear system in $(a, b, c)$
We substitute each given point $(x_i, y_i)$ into the relation $p(x_i) = a x_i^2 + b x_i + c = y_i$:
1. **For $(0, 1)$, i.e., $p(0) = 1$:**
   $$a(0)^2 + b(0) + c = 1 \implies c = 1.$$
2. **For $(1, 3)$, i.e., $p(1) = 3$:**
   $$a(1)^2 + b(1) + c = 3 \implies a + b + c = 3.$$
3. **For $(2, 9)$, i.e., $p(2) = 9$:**
   $$a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9.$$

This gives the $3\times 3$ linear system for the unknown coefficients $(a, b, c)$:
$$\begin{cases}
c = 1, \\
a + b + c = 3, \\
4a + 2b + c = 9.
\end{cases}$$
In matrix form $Ax = d$ (ordering the unknowns as $(a, b, c)$):
$$\begin{bmatrix} 0 & 0 & 1 \\ 1 & 1 & 1 \\ 4 & 2 & 1 \end{bmatrix} \begin{bmatrix} a \\ b \\ c \end{bmatrix} = \begin{bmatrix} 1 \\ 3 \\ 9 \end{bmatrix}.$$

### Step 2: Solve the linear system
Since the first equation immediately gives $c = 1$, we can either substitute $c = 1$ into the remaining two equations or perform Gaussian elimination on the augmented matrix. Let us show both clearly:

**Using Gaussian elimination on the augmented matrix (reordering rows as $R_2, R_3, R_1$):**
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 3 \\
4 & 2 & 1 & 9 \\
0 & 0 & 1 & 1
\end{array}\right]
\xrightarrow{R_2 \leftarrow R_2 - 4R_1}
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 3 \\
0 & -2 & -3 & -3 \\
0 & 0 & 1 & 1
\end{array}\right].$$

This matrix is now in upper-triangular (row echelon) form. Performing **back-substitution**:
1. From Row 3:
   $$c = 1.$$
2. Substitute $c = 1$ into Row 2 ($-2b - 3c = -3$):
   $$-2b - 3(1) = -3 \implies -2b = 0 \implies b = 0.$$
3. Substitute $b = 0$ and $c = 1$ into Row 1 ($a + b + c = 3$):
   $$a + 0 + 1 = 3 \implies a = 2.$$

### Step 3: Write the resulting polynomial
Substituting the coefficients $a = 2$, $b = 0$, and $c = 1$ into $p(x) = ax^2 + bx + c$ gives:
$$p(x) = 2x^2 + 0x + 1 = 2x^2 + 1.$$

---

## 4. Verification and Consistency Checks
We verify our polynomial $p(x) = 2x^2 + 1$ by evaluating it at the $x$-coordinate of each of the three given points:

1. **At $(0, 1)$:**
   $$p(0) = 2(0)^2 + 1 = 0 + 1 = 1 \quad (\text{matches } y = 1). \quad \checkmark$$
2. **At $(1, 3)$:**
   $$p(1) = 2(1)^2 + 1 = 2 + 1 = 3 \quad (\text{matches } y = 3). \quad \checkmark$$
3. **At $(2, 9)$:**
   $$p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9 \quad (\text{matches } y = 9). \quad \checkmark$$

All three points lie on the parabola $p(x) = 2x^2 + 1$.
