# Solution: Exercise 1 — Vector Operations and Their Meaning

## 1. Problem Statement
For $u=(2,-1,3)$ and $v=(-1,4,2)$ compute
$$u+v,\qquad u-v,\qquad 3u-2v.$$
Then verify that $(u+v)-v=u$, and explain geometrically what adding two vectors means.

---

## 2. Theoretical Background and Concepts
In three-dimensional Euclidean space $\mathbb{R}^3$, vectors represent directed displacements or quantities having both magnitude and direction. Given two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ and scalars $\alpha, \beta \in \mathbb{R}$, algebraic operations are performed component-wise:
- **Vector addition:** $u + v = (u_1 + v_1, u_2 + v_2, u_3 + v_3)$
- **Vector subtraction:** $u - v = u + (-1)v = (u_1 - v_1, u_2 - v_2, u_3 - v_3)$
- **Scalar multiplication and linear combination:** $\alpha u + \beta v = (\alpha u_1 + \beta v_1, \alpha u_2 + \beta v_2, \alpha u_3 + \beta v_3)$

Because component-wise addition inherits the associative, commutative, and inverse properties of real numbers, vector subtraction acts as the exact inverse operation of vector addition: $(u + v) - v = u + (v - v) = u + \mathbf{0} = u$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the vector sum $u + v$
Adding the corresponding coordinates of $u = (2, -1, 3)$ and $v = (-1, 4, 2)$ gives:
$$u + v = (2 + (-1),\; -1 + 4,\; 3 + 2) = (1, 3, 5).$$

### Step 2: Compute the vector difference $u - v$
Subtracting the coordinates of $v$ from the corresponding coordinates of $u$ gives:
$$u - v = (2 - (-1),\; -1 - 4,\; 3 - 2) = (2 + 1,\; -5,\; 1) = (3, -5, 1).$$

### Step 3: Compute the linear combination $3u - 2v$
First, we scale each vector by its respective scalar coefficient:
$$3u = 3(2, -1, 3) = (6, -3, 9),$$
$$2v = 2(-1, 4, 2) = (-2, 8, 4).$$
Next, we subtract $2v$ from $3u$ component by component:
$$3u - 2v = (6 - (-2),\; -3 - 8,\; 9 - 4) = (8, -11, 5).$$

### Step 4: Geometric meaning of vector addition
Geometrically, a vector represents a translation (displacement) in space:
1. **Tip-to-Tail Rule (Triangle Law):** If we start at an initial point, follow the displacement $u$, and from the terminal point (tip) of $u$ place the initial point (tail) of $v$, the sum $u + v$ is the net displacement vector from the original starting point directly to the tip of $v$.
2. **Parallelogram Law:** If $u$ and $v$ are placed tail-to-tail at the same origin, they span a parallelogram. The vector sum $u + v$ forms the main diagonal of this parallelogram starting from the common origin, while $u - v$ forms the other diagonal pointing from the tip of $v$ to the tip of $u$.

---

## 4. Verification and Consistency Checks

### Algebraic Verification of $(u + v) - v = u$
Using the computed sum $u + v = (1, 3, 5)$ and subtracting $v = (-1, 4, 2)$ explicitly:
$$(u + v) - v = (1, 3, 5) - (-1, 4, 2) = (1 - (-1),\; 3 - 4,\; 5 - 2) = (2, -1, 3) = u.$$
This confirms both the accuracy of our addition $u + v$ and the algebraic identity that subtracting $v$ reverses the displacement of adding $v$.

### Cross-Check of $3u - 2v$ Using $u$ and $u - v$
Notice that $3u - 2v$ can be rewritten as $u + 2(u - v)$:
$$u + 2(u - v) = (2, -1, 3) + 2(3, -5, 1) = (2, -1, 3) + (6, -10, 2) = (8, -11, 5),$$
which matches our result $(8, -11, 5)$ identically.
