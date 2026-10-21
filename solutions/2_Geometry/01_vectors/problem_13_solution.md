# Solution: Exercise 13 — Do Four Points Lie in One Plane?

## 1. Problem Statement
Given
$$A=(0,0,0),\qquad B=(1,2,0),\qquad C=(0,1,1),\qquad D=(2,5,1).$$

1. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Find $n=\overrightarrow{AB}\times\overrightarrow{AC}$.
3. Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD}\cdot n=0$.
4. Based on this, decide whether $D$ lies in the plane determined by $A,B,C$, and justify the criterion.

---

## 2. Theoretical Background and Concepts
Suppose three non-collinear points $A, B, C \in \mathbb{R}^3$ define a plane $\Pi$:
- The vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ span all displacements within the plane $\Pi$ starting from $A$.
- Their cross product $n = \overrightarrow{AB} \times \overrightarrow{AC} \neq \mathbf{0}$ is a **normal vector** perpendicular to $\Pi$.
- **Coplanarity Criterion:** Any fourth point $D \in \mathbb{R}^3$ lies in the plane $\Pi$ if and only if the displacement vector $\overrightarrow{AD}$ lies in $\Pi$, which occurs if and only if $\overrightarrow{AD}$ is perpendicular to the plane's normal vector $n$:
  $$D \in \Pi_{ABC} \iff \overrightarrow{AD} \perp n \iff \overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC}) = 0.$$
  Geometrically, $|\overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC})|$ is also the volume of the parallelepiped spanned by $\overrightarrow{AB}, \overrightarrow{AC}, \overrightarrow{AD}$, which vanishes if and only if the three vectors are coplanar.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$
Since $A = (0, 0, 0)$ is the origin, subtracting $A$ from $B = (1, 2, 0)$ and $C = (0, 1, 1)$ gives:
$$\overrightarrow{AB} = B - A = (1 - 0,\; 2 - 0,\; 0 - 0) = (1, 2, 0),$$
$$\overrightarrow{AC} = C - A = (0 - 0,\; 1 - 0,\; 1 - 0) = (0, 1, 1).$$

### Step 2: Find $n = \overrightarrow{AB} \times \overrightarrow{AC}$
Evaluating the cross product of $\overrightarrow{AB} = (1, 2, 0)$ and $\overrightarrow{AC} = (0, 1, 1)$:
$$n = \overrightarrow{AB} \times \overrightarrow{AC} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 0 \\ 0 & 1 & 1 \end{vmatrix} = \big((2)(1) - (0)(1),\; -[(1)(1) - (0)(0)],\; (1)(1) - (2)(0)\big) = (2, -1, 1).$$
Note that $n = (2, -1, 1) \neq \mathbf{0}$, so $A, B, C$ are non-collinear and uniquely determine a plane.

### Step 3: Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD} \cdot n = 0$
First, we construct the displacement vector from $A = (0, 0, 0)$ to $D = (2, 5, 1)$:
$$\overrightarrow{AD} = D - A = (2 - 0,\; 5 - 0,\; 1 - 0) = (2, 5, 1).$$
Next, we compute the dot product of $\overrightarrow{AD} = (2, 5, 1)$ with $n = (2, -1, 1)$:
$$\overrightarrow{AD} \cdot n = (2, 5, 1) \cdot (2, -1, 1) = (2)(2) + (5)(-1) + (1)(1) = 4 - 5 + 1 = 0.$$
Thus, $\overrightarrow{AD} \cdot n = 0$ holds identically.

### Step 4: Decision and justification of the criterion
- **Decision:** Because $\overrightarrow{AD} \cdot n = 0$, the point $D = (2, 5, 1)$ **does lie in the plane** determined by $A, B, C$ (the four points $A, B, C, D$ are coplanar).
- **Justification of the criterion:**
  1. **Normal-vector perspective:** The plane $\Pi$ through $A$ with normal $n = \overrightarrow{AB} \times \overrightarrow{AC}$ consists of *all* points $X$ in $\mathbb{R}^3$ whose displacement $\overrightarrow{AX}$ from $A$ is orthogonal to $n$. Since $n$ is perpendicular to two independent vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ in $\Pi$, the two-dimensional subspace of vectors orthogonal to $n$ is precisely $\operatorname{span}\{\overrightarrow{AB}, \overrightarrow{AC}\}$. Therefore, $\overrightarrow{AD} \cdot n = 0$ guarantees that $\overrightarrow{AD}$ has zero component normal to the plane $\Pi$ and lies entirely inside $\Pi$.
  2. **Volume perspective:** The absolute value $|\overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC})| = \|\overrightarrow{AB} \times \overrightarrow{AC}\|\,\|\overrightarrow{AD}\|\,|\cos\phi|$ equals the base area $\|\overrightarrow{AB} \times \overrightarrow{AC}\|$ times the perpendicular height $\|\overrightarrow{AD}\|\,|\cos\phi|$ of $D$ above the plane $ABC$ (the volume of the parallelepiped spanned by $\overrightarrow{AB}, \overrightarrow{AC}, \overrightarrow{AD}$). Because the base area $\|n\| = \sqrt{6} > 0$, this product is zero if and only if the perpendicular height of $D$ above the plane $ABC$ is zero, i.e., $D$ lies in the plane $ABC$.

---

## 4. Verification and Consistency Checks

### Explicit Linear Combination Check
If $D$ lies in the plane $ABC$, then $\overrightarrow{AD}$ must be expressible as a linear combination $\overrightarrow{AD} = \alpha\overrightarrow{AB} + \beta\overrightarrow{AC}$:
$$(2, 5, 1) = \alpha(1, 2, 0) + \beta(0, 1, 1) = (\alpha,\; 2\alpha + \beta,\; \beta).$$
From the first and third coordinates, $\alpha = 2$ and $\beta = 1$. Checking the middle coordinate:
$$2\alpha + \beta = 2(2) + 1 = 5,$$
which matches $\overrightarrow{AD} = (2, 5, 1)$! Thus, $\overrightarrow{AD} = 2\overrightarrow{AB} + \overrightarrow{AC}$, providing a direct constructive proof that $D$ lies in the plane $ABC$.
