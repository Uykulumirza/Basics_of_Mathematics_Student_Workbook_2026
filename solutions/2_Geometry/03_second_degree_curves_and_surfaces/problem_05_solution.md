# Solution to Exercise 5: Hyperbola and Asymptotes

## 1. Problem Statement

Given the canonical equation of the hyperbola:
$$\frac{x^2}{16} - \frac{y^2}{9} = 1$$

1. Find the intercepts with the $x$-axis (the vertices).
2. Determine the equations of the asymptotes.
3. Make a geometric sketch/plot showing the vertices, branches, and asymptotes.
4. Explain rigorously why the asymptotes describe the behavior of the curve far from the center ($|x| \to \infty$).

---

## 2. Theoretical Background and Concepts

### Canonical Equation of a Horizontal Hyperbola
The canonical form of a hyperbola centered at $(0, 0)$ with transverse axis along the $x$-axis is:
$$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$$
where:
- $a > 0$ is the length of the real semi-axis.
- $b > 0$ is the length of the imaginary semi-axis.
- $c = \sqrt{a^2 + b^2}$ is the focal distance, with foci located at $(\pm c, 0)$.

### Nature of Hyperbolic Asymptotes
Replacing the constant $1$ on the right-hand side with $0$ gives the asymptotic cone:
$$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 0 \iff y = \pm \frac{b}{a} x$$
An asymptote is a line such that the perpendicular distance from a point on the curve to the line approaches zero as the point moves infinitely far along the curve.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find Intercepts with the Coordinate Axes
- **$x$-intercepts (setting $y = 0$):**
  $$\frac{x^2}{16} - 0 = 1 \implies x^2 = 16 \implies x = \pm 4$$
  The hyperbola intersects the $x$-axis at the two vertices:
  $$V_1 = (-4, 0) \qquad \text{and} \qquad V_2 = (4, 0)$$

- **$y$-intercepts (setting $x = 0$):**
  $$0 - \frac{y^2}{9} = 1 \implies y^2 = -9$$
  Since $y^2 \ge 0$ for all real numbers, there are **no real $y$-intercepts**. The curve never crosses the $y$-axis.

---

### Step 2: Determine the Equations of the Asymptotes
From the canonical equation, $a = \sqrt{16} = 4$ and $b = \sqrt{9} = 3$.
The asymptotes are the lines:
$$y = \pm \frac{b}{a} x \implies y = \frac{3}{4}x \qquad \text{and} \qquad y = -\frac{3}{4}x$$

---

### Step 3: Compute the Foci
The focal distance is:
$$c = \sqrt{a^2 + b^2} = \sqrt{16 + 9} = \sqrt{25} = 5$$
The foci are located along the transverse $x$-axis at:
$$F_1 = (-5, 0) \qquad \text{and} \qquad F_2 = (5, 0)$$

---

### Step 4: Mathematical Explanation of Asymptotic Behavior Far From the Center
Express $y$ explicitly as a function of $x$ for the upper branch in the first quadrant ($x \ge 4$):
$$\frac{y^2}{9} = \frac{x^2}{16} - 1 \implies y = \frac{3}{4}\sqrt{x^2 - 16} = \frac{3}{4}x \sqrt{1 - \frac{16}{x^2}}$$

Now calculate the vertical difference $\Delta(x)$ between the asymptote $y_{\text{asymp}} = \frac{3}{4}x$ and the hyperbola curve $y(x)$:
$$\Delta(x) = y_{\text{asymp}} - y(x) = \frac{3}{4}x \left(1 - \sqrt{1 - \frac{16}{x^2}}\right)$$

Multiply by the conjugate $\left(1 + \sqrt{1 - \frac{16}{x^2}}\right)$:
$$\Delta(x) = \frac{3}{4}x \cdot \frac{1 - \left(1 - \frac{16}{x^2}\right)}{1 + \sqrt{1 - \frac{16}{x^2}}} = \frac{3}{4}x \cdot \frac{\frac{16}{x^2}}{1 + \sqrt{1 - \frac{16}{x^2}}} = \frac{12}{x\left(1 + \sqrt{1 - \frac{16}{x^2}}\right)}$$

Take the limit as $x \to +\infty$:
$$\lim_{x \to \infty} \Delta(x) = \lim_{x \to \infty} \frac{12}{x(1 + 1)} = \lim_{x \to \infty} \frac{6}{x} = 0$$

Because the distance shrinks to zero as $x \to \infty$, the hyperbola becomes indistinguishable from the straight lines $y = \pm \frac{3}{4}x$ far from the center.

---

### Step 5: Geometric Sketch

```
   y = -(3/4)x \             / y = (3/4)x
                \     y     /
                 \    ^    /
            *     \   |   /     *
             *     \  |  /     *
  -------*----*-----+--+--+-----*----*--------> x
        F1   V1     |  |  |    V2   F2
      (-5,0)(-4,0)  |  |  |   (4,0)(5,0)
             *     /  |  \     *
            *     /   |   \     *
                 /    |    \
                /     |     \
```

---

## 4. Verification and Consistency Checks

1. **Difference of Focal Distances (Definition of Hyperbola):**
   For any point $P$ on the hyperbola, $|d(P, F_1) - d(P, F_2)| = 2a = 8$.
   Test vertex $V_2 = (4, 0)$ with foci $F_1 = (-5, 0)$ and $F_2 = (5, 0)$:
   $$d(V_2, F_1) = |4 - (-5)| = 9$$
   $$d(V_2, F_2) = |4 - 5| = 1$$
   Difference:
   $$|9 - 1| = 8 = 2a \quad \checkmark$$

2. **Numerical Asymptote Convergence Check:**
   - At $x = 20$:
     - Hyperbola: $y = \frac{3}{4}\sqrt{400 - 16} = \frac{3}{4}\sqrt{384} \approx 14.6969$
     - Asymptote: $y = \frac{3}{4}(20) = 15$
     - Difference: $15 - 14.6969 = 0.3031$
   - At $x = 100$:
     - Hyperbola: $y = \frac{3}{4}\sqrt{10000 - 16} = \frac{3}{4}\sqrt{9984} \approx 74.93998$
     - Asymptote: $y = \frac{3}{4}(100) = 75$
     - Difference: $75 - 74.93998 = 0.06002 \approx \frac{6}{100}$
   The numerical gap matches $\frac{6}{x} = 0.06$ accurately, confirming the asymptotic behavior.
