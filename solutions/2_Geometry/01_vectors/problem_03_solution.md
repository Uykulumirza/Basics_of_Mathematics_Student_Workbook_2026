# Solution: Exercise 3 — Vector Normalization

## 1. Problem Statement
For $v=(3,4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\|=1$, reconstruct $v$ in the form $v=\|v\|e$, and explain what changes during normalization and what remains unchanged.

---

## 2. Theoretical Background and Concepts
Every non-zero vector $v \in \mathbb{R}^n$ encodes two distinct geometric attributes: its **length (magnitude)** $\|v\| > 0$ and its **direction (with orientation)**.
- **Unit Vector:** A vector $e$ is called a unit vector if its length is equal to $1$, i.e., $\|e\| = 1$.
- **Normalization:** Given any non-zero vector $v \neq \mathbf{0}$, dividing $v$ by its positive length $\|v\|$ produces a unit vector:
  $$e = \frac{1}{\|v\|}v = \frac{v}{\|v\|}.$$
  Because $\frac{1}{\|v\|} > 0$ is a positive scalar, multiplying $v$ by $\frac{1}{\|v\|}$ preserves both the line of action (direction) and the sense (orientation) of $v$, while scaling its length to $\left\|\frac{1}{\|v\|}v\right\| = \frac{1}{\|v\|}\|v\| = 1$.
- **Polar / Magnitude-Direction Decomposition:** Any non-zero vector can be factored uniquely into its magnitude and its unit direction vector:
  $$v = \|v\|e.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the magnitude $\|v\|$
For $v = (3, 4)$, the Euclidean length is:
$$\|v\| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5.$$

### Step 2: Construct the unit vector $e$
Dividing each component of $v = (3, 4)$ by $\|v\| = 5$ gives the normalized vector:
$$e = \frac{v}{\|v\|} = \frac{1}{5}(3, 4) = \left(\frac{3}{5},\; \frac{4}{5}\right) = (0.6,\; 0.8).$$

### Step 3: Check that $\|e\| = 1$
Computing the Euclidean norm of $e = \left(\frac{3}{5}, \frac{4}{5}\right)$:
$$\|e\| = \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} = \sqrt{\frac{9}{25} + \frac{16}{25}} = \sqrt{\frac{25}{25}} = \sqrt{1} = 1.$$

### Step 4: Reconstruct $v$ in the form $v = \|v\|e$
Multiplying the unit direction vector $e = \left(\frac{3}{5}, \frac{4}{5}\right)$ by the scalar magnitude $\|v\| = 5$:
$$\|v\|e = 5\left(\frac{3}{5},\; \frac{4}{5}\right) = \left(5 \cdot \frac{3}{5},\; 5 \cdot \frac{4}{5}\right) = (3, 4) = v.$$

### Step 5: Explain what changes and what remains unchanged during normalization
- **What changes:** The **magnitude (length)** of the vector changes from $\|v\| = 5$ to $\|e\| = 1$. Every coordinate is scaled uniformly by the factor $\frac{1}{\|v\|} = \frac{1}{5}$.
- **What remains unchanged:** The **direction** (the slope or ratio of components, $\frac{4/5}{3/5} = \frac{4}{3}$) and the **orientation** (pointing into the first quadrant with positive $x$- and $y$-components) remain completely unchanged because the scaling factor $\frac{1}{5}$ is strictly positive.

---

## 4. Verification and Consistency Checks

### Collinearity and Angle Check
We can verify that $v$ and $e$ point in the exact same direction by computing the cosine of the angle $\theta$ between them:
$$\cos\theta = \frac{v \cdot e}{\|v\|\,\|e\|} = \frac{3\left(\frac{3}{5}\right) + 4\left(\frac{4}{5}\right)}{5 \cdot 1} = \frac{\frac{9}{5} + \frac{16}{5}}{5} = \frac{5}{5} = 1 \implies \theta = 0.$$
An angle of $\theta = 0$ confirms that $e$ has the exact same direction and orientation as $v$.
