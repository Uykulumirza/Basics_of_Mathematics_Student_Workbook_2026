# Solution to Exercise 6: Shifted Ellipse

## 1. Problem Statement

Reduce the second-degree equation
$$4x^2 + 9y^2 - 16x + 18y - 11 = 0$$
to canonical form. Give the coordinates of the center and the lengths of the semiaxes. Check that substituting the coordinates of the center into the left-hand side of the original equation gives a value consistent with the canonical form you obtained.

---

## 2. Theoretical Background and Concepts

### Canonical Equation of a Shifted Ellipse
When an ellipse with horizontal semiaxis $a > 0$ and vertical semiaxis $b > 0$ is translated so that its center lies at $C = (x_0, y_0)$ instead of the origin, its canonical equation takes the form:
$$\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$$

### Completing the Square with Non-Unit Leading Coefficients
In a general quadratic equation $Ax^2 + By^2 + Dx + Ey + F = 0$ where $A, B > 0$ and $A \neq B$, we must first **factor out** the leading coefficient $A$ from the $x$-terms and $B$ from the $y$-terms before completing the square:
$$A(x - x_0)^2 + B(y - y_0)^2 = K$$
Every constant added inside a parenthesis is multiplied by the outer factor ($A$ or $B$) when balancing the equation. Dividing both sides by $K > 0$ then produces the standard right-hand side equal to $1$, with $a^2 = \frac{K}{A}$ and $b^2 = \frac{K}{B}$.

### Algebraic Meaning of Evaluating the Left-Hand Side at the Center
Let $P(x, y) = Ax^2 + By^2 + Dx + Ey + F$ be the original left-hand side polynomial. Before dividing by $K$, the completed-square identity is an exact polynomial identity:
$$P(x, y) = A(x - x_0)^2 + B(y - y_0)^2 - K$$
Evaluating $P(x, y)$ at the center $(x, y) = (x_0, y_0)$ causes both squared terms to vanish simultaneously, leaving the minimum value of the quadratic polynomial:
$$P(x_0, y_0) = A(0)^2 + B(0)^2 - K = -K$$
This provides a direct consistency test between the original polynomial and the completed-square form.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group Variables and Factor Out Leading Coefficients
Start with the given equation:
$$4x^2 + 9y^2 - 16x + 18y - 11 = 0$$

Group the $x$-terms and $y$-terms separately and move the constant term $-11$ to the right-hand side:
$$(4x^2 - 16x) + (9y^2 + 18y) = 11$$

Factor out $4$ from the $x$-group and $9$ from the $y$-group:
$$4(x^2 - 4x) + 9(y^2 + 2y) = 11$$

---

### Step 2: Complete the Square Inside Each Group
1. **For $x^2 - 4x$:**
   Half of $-4$ is $-2$, and $(-2)^2 = 4$. Thus:
   $$x^2 - 4x = (x - 2)^2 - 4$$
   Multiplying by the outer factor $4$:
   $$4(x^2 - 4x) = 4(x - 2)^2 - 16$$

2. **For $y^2 + 2y$:**
   Half of $+2$ is $+1$, and $1^2 = 1$. Thus:
   $$y^2 + 2y = (y + 1)^2 - 1$$
   Multiplying by the outer factor $9$:
   $$9(y^2 + 2y) = 9(y + 1)^2 - 9$$

---

### Step 3: Normalize to Canonical Form
Substitute the completed squares back into the equation:
$$4(x - 2)^2 - 16 + 9(y + 1)^2 - 9 = 11$$
Move the constants $-16$ and $-9$ to the right-hand side:
$$4(x - 2)^2 + 9(y + 1)^2 = 11 + 16 + 9$$
$$4(x - 2)^2 + 9(y + 1)^2 = 36$$

Now divide both sides of the equation by $36$ so that the right-hand side becomes $1$:
$$\frac{4(x - 2)^2}{36} + \frac{9(y + 1)^2}{36} = \frac{36}{36}$$
$$\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1$$

This is the **canonical form** of the shifted ellipse.

---

### Step 4: Read the Center and Semiaxis Lengths
Comparing $\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1$ with $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:
- **Center of the ellipse:**
  $$C = (x_0, y_0) = (2, -1)$$
- **Horizontal semiaxis length ($a$, along the $x$-direction):**
  $$a^2 = 9 \implies a = 3$$
- **Vertical semiaxis length ($b$, along the $y$-direction):**
  $$b^2 = 4 \implies b = 2$$

Since $a = 3 > b = 2$, the ellipse is elongated horizontally (parallel to the $Ox$ axis), with major vertices at $(2 \pm 3, -1) = (-1, -1)$ and $(5, -1)$, and minor co-vertices at $(2, -1 \pm 2) = (2, -3)$ and $(2, 1)$.

---

## 4. Verification and Consistency Checks

### 1. Center Substitution Check (Required by the Problem)
Let $P(x, y) = 4x^2 + 9y^2 - 16x + 18y - 11$ denote the left-hand side of the original equation.
From our completion of the square prior to dividing by $36$, we established the algebraic identity:
$$P(x, y) = 4(x - 2)^2 + 9(y + 1)^2 - 36$$

- **Substituting the center $C = (2, -1)$ into the original left-hand side:**
  $$\begin{aligned}
  P(2, -1) &= 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11 \\
  &= 4(4) + 9(1) - 32 - 18 - 11 \\
  &= 16 + 9 - 61 \\
  &= 25 - 61 = -36
  \end{aligned}$$

- **Substituting the center $C = (2, -1)$ into the unnormalized completed-square form:**
  $$4(2 - 2)^2 + 9(-1 + 1)^2 - 36 = 4(0)^2 + 9(0)^2 - 36 = -36 \quad \checkmark$$

- **In the normalized canonical form $\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} - 1 = 0$:**
  Dividing $-36$ by $36$ yields $-1$, which matches $\frac{0}{9} + \frac{0}{4} - 1 = -1$. The two forms are completely consistent.

### 2. Checking a Vertex on the Original Equation
Take the right major vertex $V_2 = (2 + 3, -1) = (5, -1)$:
- **Canonical form:** $\frac{(5 - 2)^2}{9} + \frac{(-1 + 1)^2}{4} = \frac{9}{9} + 0 = 1 \quad \checkmark$
- **Original equation:** $4(5)^2 + 9(-1)^2 - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 109 - 109 = 0 \quad \checkmark$
