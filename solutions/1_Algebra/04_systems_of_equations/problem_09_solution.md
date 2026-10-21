# Exercise 9: A System from a Sum Condition

## 1. Problem Statement
Find numbers $x,y$ satisfying
$$x+y=10,\qquad 2x+5y=32.$$
Solve the system and explain geometrically why the solution is unique.

---

## 2. Theoretical Background and Concepts
A linear equation in two variables, $ax + by = c$ with $(a, b) \ne (0, 0)$, defines a straight line in the Cartesian plane $\mathbb{R}^2$. Consequently, solving a $2\times 2$ linear system
$$\begin{cases}
a_1 x + b_1 y = c_1, \\
a_2 x + b_2 y = c_2
\end{cases}$$
is geometrically equivalent to finding all **intersection points** of the two lines $\ell_1$ and $\ell_2$.

Two lines in a plane intersect at **a single, unique point** if and only if they have **different slopes** (equivalently, their normal vectors $n_1 = (a_1, b_1)$ and $n_2 = (a_2, b_2)$ are non-collinear, i.e., $\det(A) = a_1 b_2 - a_2 b_1 \ne 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the augmented matrix and solve by Gaussian elimination
We write the system in standard form:
$$\begin{cases}
x + y = 10, \\
2x + 5y = 32,
\end{cases}$$
which has the augmented matrix:
$$[A \mid b] = \left[\begin{array}{cc|c}
1 & 1 & 10 \\
2 & 5 & 32
\end{array}\right].$$

To eliminate $x$ from the second row, we subtract twice the first row from the second row ($R_2 \leftarrow R_2 - 2R_1$):
$$(2, 5 \mid 32) - 2(1, 1 \mid 10) = (0, 3 \mid 12).$$
This yields the upper-triangular augmented matrix:
$$\left[\begin{array}{cc|c}
1 & 1 & 10 \\
0 & 3 & 12
\end{array}\right].$$

### Step 2: Back-substitution
1. From the second row ($3y = 12$):
   $$y = \frac{12}{3} = 4.$$
2. Substitute $y = 4$ into the first row ($x + y = 10$):
   $$x + 4 = 10 \implies x = 6.$$

Thus, the unique solution is:
$$(x, y) = (6, 4).$$

### Step 3: Explain geometrically why the solution is unique
In the coordinate plane $\mathbb{R}^2$, each linear equation represents a straight line. Rewriting both equations in slope-intercept form $y = mx + b$:
1. **First line ($\ell_1$):**
   $$x + y = 10 \iff y = -x + 10 \quad \left(\text{slope } m_1 = -1, \;\; y\text{-intercept } b_1 = 10\right).$$
2. **Second line ($\ell_2$):**
   $$2x + 5y = 32 \iff y = -\frac{2}{5}x + \frac{32}{5} \quad \left(\text{slope } m_2 = -\frac{2}{5}, \;\; y\text{-intercept } b_2 = \frac{32}{5} = 6.4\right).$$

Because the two lines have **distinct slopes**:
$$m_1 = -1 \ne -\frac{2}{5} = m_2$$
(equivalently, their normal vectors $n_1 = (1, 1)$ and $n_2 = (2, 5)$ are not parallel since $\det\begin{bmatrix} 1 & 1 \\ 2 & 5 \end{bmatrix} = 5 - 2 = 3 \ne 0$), the lines $\ell_1$ and $\ell_2$ are **non-parallel**. In Euclidean plane geometry, two non-parallel straight lines cross each other at **exactly one point**, which is $(6, 4)$.

---

## 4. Verification and Consistency Checks
We substitute $(x, y) = (6, 4)$ into both original conditions:
1. **First condition (sum condition):**
   $$x + y = 6 + 4 = 10 \quad (\text{matches RHS } = 10). \quad \checkmark$$
2. **Second condition (weighted sum condition):**
   $$2x + 5y = 2(6) + 5(4) = 12 + 20 = 32 \quad (\text{matches RHS } = 32). \quad \checkmark$$

Both equations hold, confirming that $(x, y) = (6, 4)$ is the unique point of intersection.
