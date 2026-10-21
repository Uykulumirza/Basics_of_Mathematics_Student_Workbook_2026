# Solution: Exercise 2 — Distance as the Length of a Vector

## 1. Problem Statement
The points are $A=(1,2,3)$ and $B=(4,-2,6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

---

## 2. Theoretical Background and Concepts
Given two points $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$ in $\mathbb{R}^3$:
- **Displacement Vector:** The directed line segment from $A$ to $B$ is represented by the difference of their position vectors relative to the origin $O$:
  $$\overrightarrow{AB} = \overrightarrow{OB} - \overrightarrow{OA} = B - A = (x_B - x_A,\; y_B - y_A,\; z_B - z_A).$$
- **Euclidean Norm (Vector Length):** For any vector $v = (v_x, v_y, v_z)$, its length (magnitude) is derived from the three-dimensional Pythagorean theorem:
  $$\|v\| = \sqrt{v_x^2 + v_y^2 + v_z^2}.$$
- **Euclidean Distance Between Points:** The distance $d(A, B)$ between points $A$ and $B$ is given by the coordinate distance formula:
  $$d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct the displacement vector $\overrightarrow{AB}$
Subtracting the coordinates of the initial point $A = (1, 2, 3)$ from the terminal point $B = (4, -2, 6)$ gives:
$$\overrightarrow{AB} = B - A = (4 - 1,\; -2 - 2,\; 6 - 3) = (3, -4, 3).$$

### Step 2: Compute the length of $\overrightarrow{AB}$
Applying the Euclidean norm formula to $\overrightarrow{AB} = (3, -4, 3)$:
$$\|\overrightarrow{AB}\| = \sqrt{3^2 + (-4)^2 + 3^2} = \sqrt{9 + 16 + 9} = \sqrt{34} \approx 5.8310.$$

### Step 3: Compute the distance between $A$ and $B$ using the coordinate formula
Substituting the coordinates of $A = (1, 2, 3)$ and $B = (4, -2, 6)$ directly into the distance formula:
$$d(A, B) = \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2} = \sqrt{3^2 + (-4)^2 + 3^2} = \sqrt{9 + 16 + 9} = \sqrt{34}.$$

### Step 4: Explain why both calculations give the same result
Both calculations yield the exact same value $\sqrt{34}$ because the Euclidean distance between two points $A$ and $B$ is **defined** geometrically as the length of the straight line segment connecting $A$ to $B$, which is precisely the magnitude of the displacement vector $\overrightarrow{AB} = B - A$. 

In the coordinate distance formula, the expressions $(x_B - x_A)$, $(y_B - y_A)$, and $(z_B - z_A)$ inside the parentheses are literally the components $(v_x, v_y, v_z)$ of the difference vector $\overrightarrow{AB}$. Computing $\overrightarrow{AB}$ first and then finding $\|\overrightarrow{AB}\|$ simply splits the exact same algebraic evaluation into two conceptual stages: finding the coordinate displacements along each axis, and applying the 3D Pythagorean theorem to those displacements.

---

## 4. Verification and Consistency Checks

### Reversal Check: Reconstructing $B$ from $A$ and $\overrightarrow{AB}$
Adding the displacement vector $\overrightarrow{AB} = (3, -4, 3)$ to the starting point $A = (1, 2, 3)$ yields:
$$A + \overrightarrow{AB} = (1 + 3,\; 2 + (-4),\; 3 + 3) = (4, -2, 6) = B.$$

### Symmetry Check: Using $\overrightarrow{BA}$
If we reverse the direction of the vector, $\overrightarrow{BA} = A - B = (-3, 4, -3)$, its length is:
$$\|\overrightarrow{BA}\| = \sqrt{(-3)^2 + 4^2 + (-3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34} = \|\overrightarrow{AB}\|,$$
confirming that distance is symmetric: $d(A, B) = d(B, A)$.
