+++
order = 4
tags = ["math", "multivariable-calculus", "arc-length", "curvature", "tnb-frame", "osculating-plane"]
+++

# Multivariable Calculus — Arc Length, Curvature, and the TNB Frame

## 4.1 Motivating problem: measuring length along a space curve

Q: Why can't we use the ordinary 1D formula $L = \int_a^b \sqrt{1 + (f'(x))^2}\,dx$ for a general space curve?
A: That formula assumes the curve is the graph of a single-valued function $y = f(x)$. A space curve $\vec{r}(t) = \langle x(t), y(t), z(t)\rangle$ can loop, cross itself, or fail the vertical line test in any coordinate. We need a formula built directly on the parametrization, not on a function graph.

Q: Before deriving an arc-length formula, predict: if a particle traces out a curve, what quantity integrated over time should give total distance traveled?
A: Speed. Distance equals speed times time for constant motion, and integrating speed over an interval generalizes this to variable motion — this is exactly the insight behind the arc-length integral.

C: The arc-length problem asks: given a parametrized curve $\vec{r}(t)$ for $t \in [a,b]$, compute the [total length] of the path traced out.

## 4.2 Arc length formula: $L = \int_a^b |\vec{r}\,'(t)|\,dt$

C: The arc length of $\vec{r}(t)$ on $[a,b]$ is $L = \int_a^b [|\vec{r}\,'(t)|]\,dt$, where $\vec{r}\,'(t)$ is the velocity vector.

C: In components, $L = \int_a^b \sqrt{[(x'(t))^2 + (y'(t))^2 + (z'(t))^2]}\,dt$, where $x(t), y(t), z(t)$ are the coordinate functions of $\vec{r}(t)$.

Q: In the formula $L = \int_a^b |\vec{r}\,'(t)|\,dt$, what does $|\vec{r}\,'(t)|$ represent physically?
A: The instantaneous speed of a particle whose position at time $t$ is $\vec{r}(t)$. Arc length is the integral of speed over time, matching the intuition "distance = speed integrated over time."

## 4.3 Why this formula works (integrating speed over time)

Q: Explain why integrating $|\vec{r}\,'(t)|$ from $a$ to $b$ gives the curve's length.
A: Over an infinitesimal time $dt$, the particle moves by the vector $\vec{r}\,'(t)\,dt$, whose magnitude $|\vec{r}\,'(t)|\,dt$ is the tiny distance traveled. Summing (integrating) these infinitesimal distances along the path accumulates the total length.

Q: Why is $|\vec{r}\,'(t)|\,dt$ a better approximation to a curve segment than the straight-line chord for small $dt$?
A: For small $dt$, the curve is nearly tangent to $\vec{r}\,'(t)$, so the tangent segment $\vec{r}\,'(t)\,dt$ and the true curve segment agree to first order. The error vanishes faster than $dt$, so the Riemann sum converges to the true length.

C: The differential arc length is $ds = [|\vec{r}\,'(t)|\,dt]$, where $ds$ is the infinitesimal length element along the curve.

## 4.4 Parametrization independence of arc length

Q: Why does arc length not depend on the parametrization chosen for the curve?
A: Arc length is a geometric property of the path itself. Under a smooth change of parameter $u = \phi(t)$, the chain rule and change-of-variables in the integral cancel exactly, leaving the same numerical length. Only the image of the curve matters, not how fast it is traced.

Q: If $\vec{r}_1(t)$ and $\vec{r}_2(u)$ trace the same curve at different speeds, how do their arc-length integrals compare?
A: They give identical values. Reparametrizing via $t = g(u)$ substitutes $|\vec{r}_1'(g(u))|\,g'(u)\,du = |\vec{r}_2'(u)|\,du$, so the integrals match. This is why length is a geometric invariant.

C: Arc length is [parametrization-independent]: reparametrizing the same curve yields the same length.

## 4.5 Arc-length function $s(t) = \int_a^t |\vec{r}\,'(u)|\,du$

C: The arc-length function $s(t) = \int_a^t [|\vec{r}\,'(u)|]\,du$ gives the length traveled along $\vec{r}$ from the starting parameter $a$ to parameter $t$.

Q: What is the derivative $ds/dt$ of the arc-length function, and why?
A: $ds/dt = |\vec{r}\,'(t)|$, the speed. By the Fundamental Theorem of Calculus applied to $s(t) = \int_a^t |\vec{r}\,'(u)|\,du$, differentiating recovers the integrand — i.e., the instantaneous rate at which arc length accumulates equals instantaneous speed.

Q: Why is $s(t)$ always non-decreasing?
A: Its derivative $|\vec{r}\,'(t)| \geq 0$ is a magnitude. Arc length only accumulates; even if the particle reverses direction, the length keeps growing because speed is non-negative.

## 4.6 Reparametrization by arc length — a canonical parametrization

Q: What does it mean to "parametrize a curve by arc length"?
A: Choose the parameter $s$ equal to the distance traveled along the curve from a fixed starting point. The new position function $\vec{r}(s)$ satisfies $|\vec{r}\,'(s)| = 1$ for all $s$ — the particle moves at unit speed.

Q: Why is arc-length parametrization called "canonical"?
A: It is determined by the curve's geometry alone (up to choice of starting point and direction), not by any arbitrary time parameter. Any two people parametrizing the same oriented curve by arc length will get the same functions.

C: In arc-length parametrization, the speed is always [1], so $|\vec{r}\,'(s)| = 1$.

## 4.7 Why arc-length parametrization simplifies curvature formulas

Q: Why do curvature formulas take their simplest form when the curve is parametrized by arc length?
A: When $|\vec{r}\,'(s)| = 1$, the tangent vector $\vec{T}$ equals $\vec{r}\,'(s)$ directly, and derivatives with respect to $s$ measure purely geometric bending rather than a mix of bending and changing speed. The speed-dependence drops out of every formula.

Q: For a general parameter $t$, the derivative $d\vec{T}/dt$ depends on both bending and speed changes. Why does $d\vec{T}/ds$ isolate pure bending?
A: Differentiating with respect to arc length removes the effect of how fast the parameter advances. Since equal increments of $s$ always correspond to equal geometric distances along the curve, $d\vec{T}/ds$ measures only how direction changes per unit length — i.e., pure turning.

## 4.8 Unit tangent vector $\vec{T}(t) = \vec{r}\,'(t)/|\vec{r}\,'(t)|$

C: The unit tangent vector is $\vec{T}(t) = [\vec{r}\,'(t)/|\vec{r}\,'(t)|]$, where $\vec{r}\,'(t)$ is the velocity; it points in the direction of motion and has length 1.

Q: Why do we normalize $\vec{r}\,'(t)$ to get $\vec{T}(t)$ rather than just using the velocity?
A: Velocity carries both direction and speed; normalizing isolates pure direction. This makes $\vec{T}$ a purely geometric object, useful for describing the shape of the curve independent of how fast it's traversed.

Q: If $\vec{r}(t)$ is parametrized by arc length $s$, what is $\vec{T}(s)$?
A: $\vec{T}(s) = \vec{r}\,'(s)$ directly, with no normalization needed, because $|\vec{r}\,'(s)| = 1$ by definition of arc-length parametrization.

## 4.9 Curvature definition: $\kappa = |d\vec{T}/ds|$

C: The curvature is defined as $\kappa = [|d\vec{T}/ds|]$, where $\vec{T}$ is the unit tangent and $s$ is arc length; it measures how fast the tangent direction turns per unit length.

Q: Why define curvature as $|d\vec{T}/ds|$ rather than $|d\vec{T}/dt|$?
A: Using $s$ (arc length) makes curvature a property of the curve itself, not of the parametrization. A curve traversed twice as fast would double $|d\vec{T}/dt|$ even though its shape is unchanged; $|d\vec{T}/ds|$ avoids this artifact.

Q: What does $\kappa = 0$ mean geometrically?
A: The tangent direction never changes, so the curve is a straight line. Any nonzero curvature indicates the curve is bending.

## 4.10 Alternative formula: $\kappa(t) = |\vec{r}\,'(t)\times\vec{r}\,''(t)|/|\vec{r}\,'(t)|^3$

C: For a general parametrization, $\kappa(t) = [|\vec{r}\,'(t)\times\vec{r}\,''(t)|/|\vec{r}\,'(t)|^3]$, where $\vec{r}\,'$ is velocity and $\vec{r}\,''$ is acceleration.

Q: Why does the formula $\kappa = |\vec{r}\,'\times\vec{r}\,''|/|\vec{r}\,'|^3$ work for ANY parametrization, not just arc length?
A: The cross product $\vec{r}\,'\times\vec{r}\,''$ isolates the component of acceleration perpendicular to velocity (pure turning), and dividing by $|\vec{r}\,'|^3$ exactly cancels the speed-dependence introduced by using $t$ instead of $s$. The formula is parametrization-invariant.

Q: What role does $\vec{r}\,'\times\vec{r}\,''$ play geometrically?
A: It is a vector perpendicular to the osculating plane whose magnitude captures how much acceleration is "sideways" relative to velocity. Parallel acceleration (speeding up along a line) gives zero cross product, correctly yielding zero curvature.

## 4.11 Curvature of a plane curve $y = f(x)$: $\kappa = |f''|/(1 + (f')^2)^{3/2}$

C: For a plane curve $y = f(x)$, the curvature is $\kappa = [|f''(x)|/(1 + (f'(x))^2)^{3/2}]$, where $f'$ and $f''$ are the first and second derivatives of $f$.

Q: Why does the plane curve formula have $(1 + (f')^2)^{3/2}$ in the denominator rather than just $1$?
A: Parametrize as $\vec{r}(x) = \langle x, f(x)\rangle$, giving $|\vec{r}\,'(x)| = \sqrt{1 + (f')^2}$. The factor of $|\vec{r}\,'|^3$ in the general formula then produces $(1 + (f')^2)^{3/2}$, correcting for the fact that arc length advances faster than $x$ when the curve is steep.

Q: At a point where $f'(x) = 0$ (horizontal tangent), what does the formula simplify to?
A: $\kappa = |f''(x)|$. At a flat tangent, the parameter $x$ coincides with arc length locally, so the second derivative directly measures bending — matching our intuition that $|f''|$ describes concavity.

## 4.12 Geometric meaning of curvature (reciprocal of osculating circle radius)

C: Curvature equals the [reciprocal] of the radius of the osculating circle: $\kappa = 1/R$, where $R$ is the radius of the best-fit tangent circle at that point.

Q: What is the osculating circle at a point on a curve?
A: The unique circle that matches the curve's position, tangent direction, and curvature at that point. It is the circle that "best approximates" the curve locally, lying in the osculating plane on the concave side.

Q: Why does a tighter turn correspond to higher curvature?
A: A tighter turn means a smaller osculating circle radius $R$. Since $\kappa = 1/R$, small $R$ yields large $\kappa$. A straight line is the limit $R \to \infty$, giving $\kappa = 0$.

## 4.13 Principal unit normal $\vec{N} = \vec{T}\,'(t)/|\vec{T}\,'(t)|$

C: The principal unit normal vector is $\vec{N}(t) = [\vec{T}\,'(t)/|\vec{T}\,'(t)|]$, where $\vec{T}(t)$ is the unit tangent; it is the unit vector in the direction the tangent is turning.

Q: Why is $\vec{T}\,'(t)$ always perpendicular to $\vec{T}(t)$?
A: Since $|\vec{T}|^2 = \vec{T}\cdot\vec{T} = 1$ is constant, differentiating gives $2\vec{T}\cdot\vec{T}\,' = 0$. So $\vec{T}\,'$ is orthogonal to $\vec{T}$, making $\vec{N}$ (its normalization) a genuine "normal" direction.

Q: Why do we normalize $\vec{T}\,'(t)$ to define $\vec{N}$?
A: $|\vec{T}\,'(t)|$ depends on the speed of parametrization and on the curvature; normalizing strips this out, leaving a pure unit direction that describes "where the curve is bending" independent of parametrization.

## 4.14 $\vec{N}$ points toward the concave side of the curve

Q: Why does $\vec{N}$ always point toward the concave (inside) side of a curve?
A: $\vec{T}$ turns toward the inside of the bend; $\vec{T}\,'$ captures this turning direction. Since $\vec{N}$ is a positive scalar multiple of $\vec{T}\,'$, it inherits this inward-pointing direction, landing on the concave side.

Q: On a circle traversed counterclockwise, does $\vec{N}$ point toward or away from the center?
A: Toward the center. The tangent rotates counterclockwise, so $\vec{T}\,'$ points radially inward; normalizing gives $\vec{N}$ also pointing to the center — the concave side of the circular arc.

C: The principal normal $\vec{N}$ points toward the [concave side] (the center of the osculating circle).

## 4.15 Binormal $\vec{B} = \vec{T}\times\vec{N}$

C: The binormal vector is $\vec{B}(t) = [\vec{T}(t)\times\vec{N}(t)]$, where $\vec{T}$ is the unit tangent and $\vec{N}$ is the principal unit normal.

Q: Why is $\vec{B}$ automatically a unit vector?
A: $\vec{T}$ and $\vec{N}$ are unit vectors that are perpendicular to each other, so $|\vec{T}\times\vec{N}| = |\vec{T}||\vec{N}|\sin(\pi/2) = 1$. The cross product of orthogonal unit vectors is a unit vector.

Q: What direction does $\vec{B}$ point for a curve lying in a plane?
A: $\vec{B}$ is constant and perpendicular to the plane. Since $\vec{T}$ and $\vec{N}$ both lie in the plane and the curve never leaves it, their cross product is fixed (up to sign) — this constancy characterizes planar curves.

## 4.16 TNB frame — an orthonormal triple moving along the curve

C: The TNB frame (or Frenet frame) consists of three mutually [orthogonal] unit vectors $\vec{T}, \vec{N}, \vec{B}$ that move with a point along the curve.

Q: Why is the TNB frame useful for analyzing space curves?
A: It provides a local coordinate system intrinsic to the curve rather than to external axes. Any vector (like acceleration) can be decomposed into TNB components that have direct geometric meaning — along the curve, toward the curvature center, or out of the osculating plane.

Q: How do we know $\vec{T}, \vec{N}, \vec{B}$ are mutually orthogonal?
A: $\vec{T}\perp\vec{N}$ because $\vec{T}\,'\perp\vec{T}$ and $\vec{N}$ is parallel to $\vec{T}\,'$. $\vec{B} = \vec{T}\times\vec{N}$ is automatically perpendicular to both $\vec{T}$ and $\vec{N}$ by the cross product's defining property.

## 4.17 Osculating plane (plane of $\vec{T}$ and $\vec{N}$), normal plane, rectifying plane

C: The [osculating plane] at a point is the plane spanned by $\vec{T}$ and $\vec{N}$; it contains the osculating circle and is the plane in which the curve is bending.

C: The [normal plane] at a point is spanned by $\vec{N}$ and $\vec{B}$, i.e., the plane perpendicular to the tangent $\vec{T}$.

C: The [rectifying plane] at a point is spanned by $\vec{T}$ and $\vec{B}$, perpendicular to the principal normal $\vec{N}$.

Q: Why is it called the "osculating" plane (from Latin "to kiss")?
A: It is the plane that locally "kisses" the curve — matching position, direction, and curvature to second order. The curve lies in this plane to second-order accuracy near the point of tangency.

## 4.18 Tangential component of acceleration $a_T = d|\vec{v}|/dt$

C: The tangential component of acceleration is $a_T = [d|\vec{v}|/dt]$, where $|\vec{v}| = |\vec{r}\,'(t)|$ is the speed; it measures how fast speed is changing.

Q: Why does $a_T$ equal the rate of change of speed rather than the full magnitude of acceleration?
A: Acceleration $\vec{a}$ has both a turning component (perpendicular to motion) and a speeding-up component (parallel to motion). Only the parallel component — projected onto $\vec{T}$ — affects speed, and that projection equals $d|\vec{v}|/dt$.

Q: When is $a_T = 0$?
A: When speed is constant (e.g., uniform circular motion). All acceleration is then purely sideways (in the $\vec{N}$ direction), changing direction but not speed.

## 4.19 Normal component of acceleration $a_N = \kappa |\vec{v}|^2$

C: The normal component of acceleration is $a_N = [\kappa |\vec{v}|^2]$, where $\kappa$ is curvature and $|\vec{v}|$ is speed; it points along $\vec{N}$ toward the curvature center.

Q: Why does $a_N$ scale as $|\vec{v}|^2$ rather than $|\vec{v}|$?
A: Going twice as fast around the same curve requires turning twice as much per unit time AND each bit of turning involves twice the velocity change. These two factors of 2 multiply to give a factor of 4 — hence $|\vec{v}|^2$. This is the same reason centripetal acceleration on a circle is $v^2/R$.

Q: Why does $a_N$ also scale linearly with $\kappa$?
A: Higher curvature means tighter turning per unit distance, requiring proportionally more sideways acceleration to produce that turning at a given speed. Doubling $\kappa$ doubles the required turning force for the same speed.

## 4.20 Decomposition $\vec{a} = a_T\vec{T} + a_N\vec{N}$

C: The acceleration decomposes as $\vec{a} = [a_T\vec{T} + a_N\vec{N}]$, with no $\vec{B}$ component, where $a_T$ is tangential and $a_N$ is normal acceleration.

Q: Why does $\vec{a}$ have no component along $\vec{B}$?
A: Differentiating $\vec{v} = |\vec{v}|\vec{T}$ by the product rule yields only $\vec{T}$ and $\vec{T}\,'$ terms. Since $\vec{T}\,'$ lies along $\vec{N}$, the resulting $\vec{a}$ lives entirely in the osculating plane — the plane of $\vec{T}$ and $\vec{N}$ — so its $\vec{B}$ component is zero.

Q: What does the fact that $\vec{a}$ lies in the osculating plane tell us about instantaneous motion?
A: At each instant the curve "bends within" the osculating plane; motion perpendicular to this plane (out along $\vec{B}$) develops only over finite time, not instantaneously. Locally, to second order, the trajectory is planar.

## 4.21 P:/S: Compute the arc length of the helix $\vec{r}(t) = \langle\cos t, \sin t, t\rangle$ from $t = 0$ to $t = 2\pi$

P: Compute the arc length of the helix $\vec{r}(t) = \langle\cos t, \sin t, t\rangle$ from $t = 0$ to $t = 2\pi$.

S:
**IDENTIFY**: Arc length of a parametrized space curve. Apply $L = \int_a^b |\vec{r}\,'(t)|\,dt$.

**PLAN**:
- Compute $\vec{r}\,'(t)$ by differentiating each component.
- Compute $|\vec{r}\,'(t)| = \sqrt{(x')^2 + (y')^2 + (z')^2}$.
- Integrate over $t \in [0, 2\pi]$.

**EXECUTE**:
1. $\vec{r}\,'(t) = \langle -\sin t, \cos t, 1\rangle$.
2. $|\vec{r}\,'(t)| = \sqrt{\sin^2 t + \cos^2 t + 1} = \sqrt{1 + 1} = \sqrt{2}$.
3. $L = \int_0^{2\pi}\sqrt{2}\,dt = \sqrt{2}\cdot 2\pi = 2\pi\sqrt{2}$.

**EVALUATE**:
- Speed is constant ($\sqrt{2}$), so arc length = speed × time = $\sqrt{2}\cdot 2\pi$.
- One turn of a helix of radius 1 projects to a circle of circumference $2\pi$ and rises by $2\pi$; by Pythagoras the actual length is $\sqrt{(2\pi)^2 + (2\pi)^2} = 2\pi\sqrt{2}$. ✓

## 4.22 P:/S: Find the curvature of $y = x^3$ at $x = 1$

P: Find the curvature of the plane curve $y = x^3$ at $x = 1$.

S:
**IDENTIFY**: Curvature of a graph $y = f(x)$. Use $\kappa = |f''(x)|/(1 + (f'(x))^2)^{3/2}$.

**PLAN**:
- Differentiate: $f'(x)$, then $f''(x)$.
- Evaluate both at $x = 1$.
- Plug into the plane-curve curvature formula.

**EXECUTE**:
1. $f(x) = x^3 \Rightarrow f'(x) = 3x^2 \Rightarrow f''(x) = 6x$.
2. At $x = 1$: $f'(1) = 3$ and $f''(1) = 6$.
3. $\kappa(1) = \dfrac{|6|}{(1 + 3^2)^{3/2}} = \dfrac{6}{10^{3/2}} = \dfrac{6}{10\sqrt{10}} = \dfrac{3}{5\sqrt{10}}$.

**EVALUATE**:
- Rationalizing: $\kappa(1) = \dfrac{3\sqrt{10}}{50} \approx 0.190$.
- Sanity check: the osculating circle radius is $R = 1/\kappa \approx 5.27$, which is reasonable — the cubic is steep at $x = 1$ (slope 3), so it bends gently along its arc length even though $f''$ is moderate.
