# Solution to Exercise 1: Recognizing Curves from Canonical Form

## 1. Problem Statement

Recognize the geometric curves described by the following canonical second-degree equations:
1. $x^2 + y^2 = 9$
2. $\frac{x^2}{16} + \frac{y^2}{9} = 1$
3. $y^2 = 8x$
4. $\frac{x^2}{9} - \frac{y^2}{4} = 1$

For each curve:
- Identify the type of conic section and its most important geometric features (center/vertex, axes, intercepts, foci, asymptotes).
- Explain which structural algebraic features of the equation reveal the type of curve.
- Provide a geometric sketch/plot.

---

## 2. Theoretical Background and Concepts

### General Second-Degree Equation in Two Variables
A plane second-degree curve is the locus of points satisfying:
$$A x^2 + B xy + C y^2 + D x + E y + F = 0$$
When there are no cross-terms ($B = 0$) and the center is at the origin ($D = E = 0$), the equation takes its standard **canonical form**.

### Classification Criteria from Equation Structure:
1. **Circle ($A = C > 0$):** $x^2 + y^2 = R^2$. Both variables are squared with identical positive coefficients.
2. **Ellipse ($A > 0, C > 0, A \ne C$):** $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$. Both variables are squared with positive but unequal coefficients.
3. **Parabola ($A = 0$ or $C = 0$):** $y^2 = 2px$ or $x^2 = 2py$. Exactly one variable is squared and the other appears linearly to degree 1.
4. **Hyperbola ($A \cdot C < 0$):** $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ or $\frac{y^2}{a^2} - \frac{x^2}{b^2} = 1$. Both variables are squared with opposite algebraic signs (one positive, one negative).

---

## 3. Detailed Step-by-Step Solution

### Curve 1: $x^2 + y^2 = 9$

- **Type of Curve:** **Circle**.
- **Algebraic Recognition:** Both $x^2$ and $y^2$ have equal coefficients ($+1$).
- **Geometric Features:**
  - Standard form: $(x - 0)^2 + (y - 0)^2 = R^2$ with $R^2 = 9 \implies R = 3$.
  - **Center:** Origin $(0, 0)$.
  - **Radius:** $R = 3$.
  - **Intercepts:**
    - $x$-intercepts ($y = 0$): $(\pm 3, 0)$.
    - $y$-intercepts ($x = 0$): $(0, \pm 3)$.
  - **Symmetry:** Complete rotational symmetry about $(0, 0)$ and reflections across both coordinate axes.

```
              y
              ^
              |
              * (0, 3)
          *   |   *
        *     |     *
  ------*-----+-----*------> x
     (-3,0)   |(0,0) (3,0)
        *     |     *
          *   |   *
              * (0, -3)
              |
```

---

### Curve 2: $\frac{x^2}{16} + \frac{y^2}{9} = 1$

- **Type of Curve:** **Ellipse** (horizontal major axis).
- **Algebraic Recognition:** Both $x^2$ and $y^2$ appear with positive coefficients, but the denominators are unequal ($16 \ne 9$). Because the larger denominator is under $x^2$, the ellipse is elongated horizontally.
- **Geometric Features:**
  - Standard form: $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$.
  - **Center:** $(0, 0)$.
  - **Semi-major axis:** $a = \sqrt{16} = 4$ along the $x$-axis.
  - **Semi-minor axis:** $b = \sqrt{9} = 3$ along the $y$-axis.
  - **Vertices on major axis:** $V_1 = (-4, 0)$ and $V_2 = (4, 0)$.
  - **Co-vertices on minor axis:** $B_1 = (0, -3)$ and $B_2 = (0, 3)$.
  - **Linear Eccentricity (Focal distance):**
    $$c = \sqrt{a^2 - b^2} = \sqrt{16 - 9} = \sqrt{7} \approx 2.65$$
  - **Foci:** $F_1 = (-\sqrt{7}, 0)$ and $F_2 = (\sqrt{7}, 0)$.

```
             y
             ^
             |    (0,3)
       * * * | * * *
    *        |        *
  *    F1    |   F2     *
--*----------+----------*--> x
(-4,0)       |        (4,0)
    *        |        *
       * * * | * * *
             |   (0,-3)
```

---

### Curve 3: $y^2 = 8x$

- **Type of Curve:** **Parabola** (horizontal axis of symmetry).
- **Algebraic Recognition:** Only $y$ is squared ($y^2$), while $x$ appears to the first power ($x^1$). The positive coefficient ($+8$) indicates it opens toward positive $x$.
- **Geometric Features:**
  - Standard form: $y^2 = 2px$ where $2p = 8 \implies p = 4$.
  - **Vertex:** $(0, 0)$.
  - **Axis of symmetry:** The $x$-axis ($y = 0$).
  - **Opening direction:** To the right ($x \ge 0$).
  - **Focus:** $F = \left(\frac{p}{2}, 0\right) = (2, 0)$.
  - **Directrix line:** $x = -\frac{p}{2} = -2$.
  - **Reference Points:**
    - For $x = 2$: $y^2 = 16 \implies y = \pm 4$, points $(2, 4)$ and $(2, -4)$ (endpoints of the latus rectum).
    - For $x = 8$: $y^2 = 64 \implies y = \pm 8$.

```
   Directrix: x = -2
           |             y
           |             ^
           |             |            * (2, 4)
           |             |          * :
           |             |        *   :
           |             |      *     :
   --------+-------------*------------+---------> x
    x = -2 |             | V(0,0)   F(2,0)
           |             |      *     :
           |             |        *   :
           |             |          * :
           |             |            * (2, -4)
           |             |
```

---

### Curve 4: $\frac{x^2}{9} - \frac{y^2}{4} = 1$

- **Type of Curve:** **Hyperbola** (horizontal transverse axis).
- **Algebraic Recognition:** Both variables are squared, but separated by a minus sign ($x^2$ is positive, $y^2$ is negative). The positive sign precedes $x^2$, meaning the hyperbola opens horizontally along the $x$-axis.
- **Geometric Features:**
  - Standard form: $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$.
  - **Center:** $(0, 0)$.
  - **Real semi-axis:** $a = \sqrt{9} = 3$.
  - **Imaginary semi-axis:** $b = \sqrt{4} = 2$.
  - **Vertices:** $V_1 = (-3, 0)$ and $V_2 = (3, 0)$.
  - **$y$-intercepts:** None (setting $x = 0$ yields $-y^2/4 = 1$, which has no real solutions).
  - **Asymptotes:** The lines given by $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 0 \implies y = \pm \frac{b}{a} x$:
    $$y = \frac{2}{3}x \qquad \text{and} \qquad y = -\frac{2}{3}x$$
  - **Linear Eccentricity (Focal distance):**
    $$c = \sqrt{a^2 + b^2} = \sqrt{9 + 4} = \sqrt{13} \approx 3.61$$
  - **Foci:** $F_1 = (-\sqrt{13}, 0)$ and $F_2 = (\sqrt{13}, 0)$.

```
  asymptote: y = -(2/3)x \     y     / asymptote: y = (2/3)x
                          \    ^    /
              *            \   |   /            *
                *           \  |  /           *
      F1          *          \ | /          *          F2
  ----+------------*----------\+-----------*------------+-----> x
    (-√13,0)     (-3,0)        |         (3,0)        (√13,0)
                  *           /|\           *
                *            / | \            *
              *             /  |  \             *
                           /   |   \
```

---

## 4. Verification and Consistency Checks

1. **Point Substitution Consistency:**
   - **Circle:** Point $(0, 3) \implies 0^2 + 3^2 = 9 = 9 \checkmark$. Point $(3/\sqrt{2}, 3/\sqrt{2}) \implies 9/2 + 9/2 = 9 \checkmark$.
   - **Ellipse:** Point $(4, 0) \implies \frac{16}{16} + 0 = 1 \checkmark$. Point $(0, 3) \implies 0 + \frac{9}{9} = 1 \checkmark$.
   - **Parabola:** Point $(2, 4) \implies 4^2 = 16 = 8(2) \checkmark$. Point $(8, 8) \implies 8^2 = 64 = 8(8) \checkmark$.
   - **Hyperbola:** Point $(3, 0) \implies \frac{9}{9} - 0 = 1 \checkmark$. Point $(3\sqrt{2}, 2) \implies \frac{18}{9} - \frac{4}{4} = 2 - 1 = 1 \checkmark$.

2. **Asymptote Behavior Check for Hyperbola:**
   For large $x \gg 1$:
   $$y = \pm 2 \sqrt{\frac{x^2}{9} - 1} = \pm \frac{2}{3} x \sqrt{1 - \frac{9}{x^2}} \approx \pm \frac{2}{3} x \left(1 - \frac{9}{2x^2}\right) \to \pm \frac{2}{3}x$$
   The distance between the hyperbola branch and the lines $y = \pm \frac{2}{3}x$ approaches $0$ as $x \to \infty$, confirming the asymptotes.

