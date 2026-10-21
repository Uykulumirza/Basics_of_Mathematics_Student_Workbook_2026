# Exercise 15: Complete Classification of a Line Relative to a Plane — Solution

## 1. Problem Statement

Let
$$L:p+tv,\qquad \Pi:n\cdot x=d.$$
State the conditions distinguishing the three cases: one intersection point, parallel with no common points, and the line contained in the plane. Then illustrate each case with your own simple numerical example.

---

## 2. Theoretical Background and Concepts

Let $L$ be a line in $\mathbb{R}^3$ with base point $p \in \mathbb{R}^3$ and non-zero direction vector $v \in \mathbb{R}^3 \setminus \{\mathbf{0}\}$:
$$L = \{x(t) = p + t v : t \in \mathbb{R}\}.$$
Let $\Pi$ be a plane in $\mathbb{R}^3$ with non-zero normal vector $n \in \mathbb{R}^3 \setminus \{\mathbf{0}\}$ and scalar constant $d \in \mathbb{R}$:
$$\Pi = \{x \in \mathbb{R}^3 : n \cdot x = d\}.$$

### Algebraic Reduction to a Single Linear Equation in $t$
A point $x(t) = p + t v$ on the line $L$ belongs to the plane $\Pi$ if and only if $t \in \mathbb{R}$ satisfies:
$$n \cdot (p + t v) = d.$$
Using the bilinearity (distributivity and scalar pull-out) of the dot product, we expand this into standard linear form $\alpha t = \beta$:
$$n \cdot p + t(n \cdot v) = d \iff (n \cdot v)\,t = d - n \cdot p.$$
Every possible geometric relationship between $L$ and $\Pi$ is governed by two scalar quantities:
1. **The directional dot product $\alpha = n \cdot v$:** Measures the rate at which the line moves in the direction normal to the plane. Geometrically, $n \cdot v = 0 \iff v \perp n \iff$ the line's direction is parallel to the plane $\Pi$.
2. **The base-point residual $\beta = d - n \cdot p$ (or $n \cdot p - d$):** Measures whether the base point $p$ itself lies on the plane $\Pi$. Specifically, $n \cdot p = d \iff p \in \Pi$.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Complete Classification Criterion

Solving $(n \cdot v)\,t = d - n \cdot p$ for $t \in \mathbb{R}$ yields exactly three mutually exclusive and exhaustive cases:

| Case | Geometric Relationship | Algebraic Condition on $n, v, p, d$ | Solution Set for Parameter $t$ | Intersection Set $L \cap \Pi$ |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **Unique Intersection Point** (line pierces the plane) | $n \cdot v \neq 0$ | Unique parameter $t^* = \dfrac{d - n \cdot p}{n \cdot v}$ | Single point $\left\{p + \dfrac{d - n \cdot p}{n \cdot v}v\right\}$ |
| **2** | **Strictly Parallel** (parallel with no common points) | $n \cdot v = 0 \quad \text{and} \quad n \cdot p \neq d$ | No solution ($0 \cdot t = d - n \cdot p \neq 0$) | Empty set $\emptyset$ |
| **3** | **Line Contained in the Plane** ($L \subset \Pi$) | $n \cdot v = 0 \quad \text{and} \quad n \cdot p = d$ | All $t \in \mathbb{R}$ ($0 \cdot t = 0$) | Entire line $L$ |

#### Detailed Explanation of the Three Cases
1. **Case 1: One Intersection Point ($n \cdot v \neq 0$)**
   - **Condition:** $n \cdot v \neq 0$ (regardless of whether $n \cdot p = d$ or $n \cdot p \neq d$).
   - **Geometric Mechanism:** Because $v$ is not orthogonal to $n$, the line is inclined relative to the plane. We can divide by the non-zero scalar $n \cdot v$ to find the unique parameter value
     $$t^* = \frac{d - n \cdot p}{n \cdot v},$$
     producing the unique intersection point $x^* = p + \left(\frac{d - n \cdot p}{n \cdot v}\right)v$. (Note: If $n \cdot p = d$ as well, then $t^* = 0$ and the unique intersection point is the base point $p$ itself.)

2. **Case 2: Parallel with No Common Points ($n \cdot v = 0$ and $n \cdot p \neq d$)**
   - **Condition:** $n \cdot v = 0$ and $n \cdot p - d \neq 0$.
   - **Geometric Mechanism:** Because $n \cdot v = 0$, the direction vector $v$ is perpendicular to the normal $n$ and therefore parallel to the plane $\Pi$. Because $n \cdot p \neq d$, the starting point $p$ lies outside $\Pi$ at a positive perpendicular distance $\frac{|n \cdot p - d|}{\|n\|} > 0$. Since moving in direction $v$ never changes $n \cdot x(t)$, the line remains at this constant non-zero distance and never meets $\Pi$.

3. **Case 3: Line Contained in the Plane ($n \cdot v = 0$ and $n \cdot p = d$)**
   - **Condition:** $n \cdot v = 0$ and $n \cdot p - d = 0$.
   - **Geometric Mechanism:** The base point $p$ lies in the plane $\Pi$ ($n \cdot p = d$), and the direction vector $v$ is parallel to the plane ($n \cdot v = 0$). Starting at a point in the plane and moving purely parallel to the plane keeps the line inside $\Pi$ for all $t \in \mathbb{R}$.

---

### Part 2: Concrete Numerical Examples in $\mathbb{R}^3$

For clarity, let us fix the horizontal plane $\Pi: z = 2$, which is written in the form $n \cdot x = d$ with:
$$n = (0, 0, 1), \qquad d = 2.$$

#### Example for Case 1 (Unique Intersection Point: $n \cdot v \neq 0$)
- **Choose line $L_1$:** Base point $p = (1, 2, 0)$ and direction vector $v = (0, 0, 1)$, so:
  $$L_1: (x, y, z) = (1, 2, 0) + t(0, 0, 1) = (1, 2, t).$$
- **Check conditions:**
  $$n \cdot v = (0, 0, 1) \cdot (0, 0, 1) = 1 \neq 0, \qquad n \cdot p = (0, 0, 1) \cdot (1, 2, 0) = 0.$$
- **Compute intersection:**
  $$t^* = \frac{d - n \cdot p}{n \cdot v} = \frac{2 - 0}{1} = 2 \implies x^* = (1, 2, 0) + 2(0, 0, 1) = (1, 2, 2).$$

#### Example for Case 2 (Parallel with No Common Points: $n \cdot v = 0$ and $n \cdot p \neq d$)
- **Choose line $L_2$:** Base point $p = (1, 2, 0)$ and direction vector $v = (1, 0, 0)$, so:
  $$L_2: (x, y, z) = (1, 2, 0) + t(1, 0, 0) = (1 + t, \, 2, \, 0).$$
- **Check conditions:**
  $$n \cdot v = (0, 0, 1) \cdot (1, 0, 0) = 0, \qquad n \cdot p = (0, 0, 1) \cdot (1, 2, 0) = 0 \neq 2 = d.$$
- **Result:** Substituting into $z = 2$ gives $0 \cdot t = 2$ ($0 = 2$), which has no solution. The line $L_2$ lies at height $z = 0$ and is strictly parallel to the plane $z = 2$.

#### Example for Case 3 (Line Contained in the Plane: $n \cdot v = 0$ and $n \cdot p = d$)
- **Choose line $L_3$:** Base point $p = (1, 2, 2)$ and direction vector $v = (1, 0, 0)$, so:
  $$L_3: (x, y, z) = (1, 2, 2) + t(1, 0, 0) = (1 + t, \, 2, \, 2).$$
- **Check conditions:**
  $$n \cdot v = (0, 0, 1) \cdot (1, 0, 0) = 0, \qquad n \cdot p = (0, 0, 1) \cdot (1, 2, 2) = 2 = d.$$
- **Result:** Substituting into $z = 2$ gives $2 + 0t = 2$ ($2 = 2$), which holds for every $t \in \mathbb{R}$. The entire line $L_3$ lies inside the plane $z = 2$.

---

## 4. Verification and Consistency Checks

Let us verify all three numerical examples by direct substitution of $x(t) = (x(t), y(t), z(t))$ into the plane equation $n \cdot x = z = 2$:
1. **For $L_1: (1, 2, t)$:** The plane equation $z = 2$ becomes $t = 2$, satisfied uniquely at $t = 2$, yielding $(1, 2, 2) \in \Pi$. $\checkmark$
2. **For $L_2: (1 + t, 2, 0)$:** The plane equation $z = 2$ becomes $0 = 2$, which is false for all $t \in \mathbb{R}$, confirming $L_2 \cap \Pi = \emptyset$. $\checkmark$
3. **For $L_3: (1 + t, 2, 2)$:** The plane equation $z = 2$ becomes $2 = 2$, which is true for all $t \in \mathbb{R}$, confirming $L_3 \subset \Pi$. $\checkmark$
