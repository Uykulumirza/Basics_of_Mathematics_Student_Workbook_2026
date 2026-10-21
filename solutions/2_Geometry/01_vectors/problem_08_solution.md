# Solution: Exercise 8 — Linear Combination and Checking the Result

## 1. Problem Statement
Check whether $w=(5,1)$ can be written as
$$w=au+bv,$$
where $u=(1,1)$ and $v=(2,-1)$. If so, find $a,b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

---

## 2. Theoretical Background and Concepts
- **Linear Combination:** A vector $w \in \mathbb{R}^2$ is a linear combination of $u$ and $v$ if there exist scalars $a, b \in \mathbb{R}$ such that
  $$w = au + bv.$$
- **Coordinate System Equivalence:** Writing $w = au + bv$ in component form produces a system of two linear equations in two unknowns $(a, b)$.
- **Basis and Span in $\mathbb{R}^2$:** Two vectors $u, v \in \mathbb{R}^2$ that are **non-collinear** (neither is a scalar multiple of the other) are linearly independent and form a **basis** of $\mathbb{R}^2$. Geometrically, they define an oblique coordinate grid across the plane, guaranteeing that *every* vector $w \in \mathbb{R}^2$ can be expressed **uniquely** as $w = au + bv$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the linear system for $a$ and $b$
Substituting $w = (5, 1)$, $u = (1, 1)$, and $v = (2, -1)$ into the vector equation $au + bv = w$:
$$a(1, 1) + b(2, -1) = (5, 1) \implies (a + 2b,\; a - b) = (5, 1).$$
Equating the first and second coordinates yields the $2 \times 2$ linear system:
$$\begin{cases}
a + 2b = 5 & \text{(Equation 1)} \\
a - b = 1  & \text{(Equation 2)}
\end{cases}$$

### Step 2: Solve for $a$ and $b$
Subtracting Equation 2 from Equation 1 eliminates $a$:
$$(a + 2b) - (a - b) = 5 - 1 \implies 3b = 4 \implies b = \frac{4}{3}.$$
Substituting $b = \frac{4}{3}$ into Equation 2 gives $a$:
$$a = 1 + b = 1 + \frac{4}{3} = \frac{7}{3}.$$
Thus, $w$ **can** be written as $w = au + bv$ with the unique coefficients:
$$a = \frac{7}{3},\qquad b = \frac{4}{3}.$$

### Step 3: Reconstruct $w$ from $a$ and $b$
Computing the linear combination $\frac{7}{3}u + \frac{4}{3}v$ explicitly:
$$\frac{7}{3}u + \frac{4}{3}v = \frac{7}{3}(1, 1) + \frac{4}{3}(2, -1) = \left(\frac{7}{3},\; \frac{7}{3}\right) + \left(\frac{8}{3},\; -\frac{4}{3}\right) = \left(\frac{7 + 8}{3},\; \frac{7 - 4}{3}\right) = \left(\frac{15}{3},\; \frac{3}{3}\right) = (5, 1) = w.$$

### Step 4: Explain the geometric meaning of the existence of $(a, b)$
Geometrically:
1. Because $u = (1, 1)$ (slope $1$) and $v = (2, -1)$ (slope $-\frac{1}{2}$) point in **non-collinear** (independent) directions, their lines of action span the entire two-dimensional plane $\mathbb{R}^2$.
2. To reach the terminal point $(5, 1)$ from the origin $(0, 0)$, we can travel $\frac{7}{3}$ units (in units of length $\|u\|$) along the direction of $u$ to the point $\left(\frac{7}{3}, \frac{7}{3}\right)$, and from there travel $\frac{4}{3}$ units (in units of length $\|v\|$) parallel to the direction of $v$ to arrive at $(5, 1)$.
3. Equivalently, if we draw lines through the origin along $u$ and $v$, and lines through $w = (5, 1)$ parallel to $u$ and $v$, they form a **parallelogram** with sides $\frac{7}{3}u$ and $\frac{4}{3}v$ and diagonal $w$. Thus, $(a, b) = \left(\frac{7}{3}, \frac{4}{3}\right)$ are the unique coordinates of $w$ in the basis $\{u, v\}$.

---

## 4. Verification and Consistency Checks

### Determinant / Cramer's Rule Check
The coefficient matrix $M = \begin{pmatrix} 1 & 2 \\ 1 & -1 \end{pmatrix}$ has determinant:
$$\det(M) = (1)(-1) - (2)(1) = -1 - 2 = -3 \neq 0,$$
confirming that $u$ and $v$ are linearly independent. By Cramer's Rule:
$$a = \frac{\det\begin{pmatrix} 5 & 2 \\ 1 & -1 \end{pmatrix}}{-3} = \frac{-5 - 2}{-3} = \frac{7}{3},\qquad b = \frac{\det\begin{pmatrix} 1 & 5 \\ 1 & 1 \end{pmatrix}}{-3} = \frac{1 - 5}{-3} = \frac{4}{3},$$
which agrees completely with our elimination solution.
