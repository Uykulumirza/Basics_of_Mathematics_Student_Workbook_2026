# Solution to Problem 7: A Trigonometric Function

## 1. Problem Statement
On $[0,2\pi]$, find the intervals of monotonicity and the extrema of
$$f(x)=\sin x+\cos x.$$
Include the endpoints of the interval and compare the function values at the critical points and at the endpoints.

> **Why this problem:** it practices the analysis of a periodic function on a bounded interval.

---

## 2. Theoretical Background and Concepts
1. **Extrema on a Closed Bounded Interval (Weierstrass Extreme Value Theorem):** A continuous function $f$ on a compact interval $[a, b]$ attains both a global maximum and a global minimum on $[a, b]$. These extreme values can occur either at:
   - **Interior critical points** $x_0 \in (a, b)$ where $f'(x_0) = 0$ (or $f'(x_0)$ does not exist), or
   - **Boundary endpoints** $x = a$ and $x = b$.
2. **Harmonic Addition Identity:** Any linear combination $\sin x + \cos x$ can be written as a single phase-shifted sine wave:
   $$\sin x + \cos x = \sqrt{2}\left(\frac{1}{\sqrt{2}}\sin x + \frac{1}{\sqrt{2}}\cos x\right) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right),$$
   which provides a geometric verification of the calculus results.

---

## 3. Detailed Step-by-Step Solution

### Step 1: First Derivative and Critical Points in $[0, 2\pi]$
The function $f(x) = \sin x + \cos x$ is continuous on $[0, 2\pi]$ and differentiable on $(0, 2\pi)$, with derivative:
$$f'(x) = \cos x - \sin x.$$
Setting $f'(x) = 0$ on $[0, 2\pi]$:
$$\cos x - \sin x = 0 \iff \sin x = \cos x.$$
Note that if $\cos x = 0$, then $\sin x = \pm 1 \neq 0$, so $\cos x \neq 0$ at any solution. Dividing both sides by $\cos x$ gives:
$$\tan x = 1.$$
On the interval $[0, 2\pi]$, the equation $\tan x = 1$ has exactly two solutions (in Quadrant I and Quadrant III):
$$x_1 = \frac{\pi}{4} \quad \text{and} \quad x_2 = \pi + \frac{\pi}{4} = \frac{5\pi}{4}.$$

### Step 2: Sign Analysis of $f'(x)$ and Intervals of Monotonicity
We can also rewrite $f'(x)$ using the cosine addition formula as $f'(x) = \sqrt{2}\cos\left(x + \frac{\pi}{4}\right)$, or compare $\cos x$ and $\sin x$ directly on the three subintervals of $[0, 2\pi]$ partitioned by $x_1 = \frac{\pi}{4}$ and $x_2 = \frac{5\pi}{4}$:
- On $\left[0, \frac{\pi}{4}\right)$: $\cos x > \sin x \implies f'(x) = \cos x - \sin x > 0$ (for example, at $x = 0$, $f'(0) = 1 > 0$).
- On $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$: $\cos x < \sin x \implies f'(x) = \cos x - \sin x < 0$ (for example, at $x = \frac{\pi}{2}$, $f'\left(\frac{\pi}{2}\right) = -1 < 0$).
- On $\left(\frac{5\pi}{4}, 2\pi\right]$: $\cos x > \sin x \implies f'(x) = \cos x - \sin x > 0$ (for example, at $x = \frac{3\pi}{2}$, $f'\left(\frac{3\pi}{2}\right) = +1 > 0$).

| Point / Interval | $x = 0$ | $\left(0, \frac{\pi}{4}\right)$ | $x = \frac{\pi}{4}$ | $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$ | $x = \frac{5\pi}{4}$ | $\left(\frac{5\pi}{4}, 2\pi\right)$ | $x = 2\pi$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f'(x)$** | $+1$ | $+$ | $0$ | $-$ | $0$ | $+$ | $+1$ |
| **Behavior of $f(x)$** | $1$ | $\nearrow$ (increasing) | **Max** ($\sqrt{2}$) | $\searrow$ (decreasing) | **Min** ($-\sqrt{2}$) | $\nearrow$ (increasing) | $1$ |

Thus, including the endpoints by continuity:
- $f$ is **strictly increasing** on $\left[0, \frac{\pi}{4}\right]$ and on $\left[\frac{5\pi}{4}, 2\pi\right]$.
- $f$ is **strictly decreasing** on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.

### Step 3: Comparison of Function Values at Critical Points and Endpoints
We evaluate $f(x) = \sin x + \cos x$ at the two interior critical points and the two boundary endpoints:
1. **Left endpoint ($x = 0$):**
   $$f(0) = \sin 0 + \cos 0 = 0 + 1 = 1.$$
2. **First critical point ($x = \frac{\pi}{4}$):**
   $$f\left(\frac{\pi}{4}\right) = \sin\frac{\pi}{4} + \cos\frac{\pi}{4} = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2} = \sqrt{2} \approx 1.414.$$
3. **Second critical point ($x = \frac{5\pi}{4}$):**
   $$f\left(\frac{5\pi}{4}\right) = \sin\frac{5\pi}{4} + \cos\frac{5\pi}{4} = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} \approx -1.414.$$
4. **Right endpoint ($x = 2\pi$):**
   $$f(2\pi) = \sin(2\pi) + \cos(2\pi) = 0 + 1 = 1.$$

**Summary of Extrema on $[0, 2\pi]$:**
- **Interior Local and Global Maximum:** Attained at $x = \frac{\pi}{4}$ with value $f\left(\frac{\pi}{4}\right) = \sqrt{2}$.
- **Interior Local and Global Minimum:** Attained at $x = \frac{5\pi}{4}$ with value $f\left(\frac{5\pi}{4}\right) = -\sqrt{2}$.
- **Boundary Endpoint Values:** At $x = 0$, the function starts at $f(0) = 1$ (which is a one-sided boundary local minimum on $\left[0, \frac{\pi}{4}\right]$), and at $x = 2\pi$, the function ends at $f(2\pi) = 1$ (which is a one-sided boundary local maximum on $\left[\frac{5\pi}{4}, 2\pi\right]$). By $2\pi$-periodicity, $f(0) = f(2\pi) = 1$, and both endpoint values lie strictly between the interior global minimum $-\sqrt{2}$ and the interior global maximum $\sqrt{2}$:
  $$-\sqrt{2} < 1 < \sqrt{2}.$$

---

## 4. Verification and Consistency Checks
1. **Phase-Shift Formula Verification:**
   Using $f(x) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right)$, as $x$ ranges over $[0, 2\pi]$, the phase angle $\theta = x + \frac{\pi}{4}$ ranges over $\left[\frac{\pi}{4}, \frac{9\pi}{4}\right]$:
   - $\sin\theta$ reaches its maximum $+1$ at $\theta = \frac{\pi}{2} \iff x = \frac{\pi}{4}$, giving $f_{\max} = \sqrt{2}$.
   - $\sin\theta$ reaches its minimum $-1$ at $\theta = \frac{3\pi}{2} \iff x = \frac{5\pi}{4}$, giving $f_{\min} = -\sqrt{2}$.
2. **Second Derivative Test:**
   $$f''(x) = -\sin x - \cos x = -f(x).$$
   - $f''\left(\frac{\pi}{4}\right) = -\sqrt{2} < 0 \implies$ strict local maximum at $x = \frac{\pi}{4}$.
   - $f''\left(\frac{5\pi}{4}\right) = +\sqrt{2} > 0 \implies$ strict local minimum at $x = \frac{5\pi}{4}$.
