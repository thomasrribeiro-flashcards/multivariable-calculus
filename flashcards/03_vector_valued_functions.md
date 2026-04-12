+++
order = 3
tags = ["math", "multivariable-calculus", "vector-functions", "space-curves", "velocity", "acceleration"]
+++

# Multivariable Calculus — Vector-Valued Functions and Space Curves

## 3.1 What a Vector-Valued Function Is

Q: Why do we need vector-valued functions in multivariable calculus, given that we already have scalar functions like $y = f(x)$?
A: A single scalar output only describes one number per input, so it cannot represent a particle's path through space, which requires multiple coordinates that all change with one parameter. A vector-valued function packages several scalar functions of the same variable into one object $\vec{r}(t)$, letting us model curves and motion with a single expression whose derivative, integral, and magnitude all have direct geometric meaning.

C: A [vector-valued function] is a function whose inputs are scalars and whose outputs are vectors.

C: A vector-valued function from $\mathbb{R}$ to $\mathbb{R}^n$ is written $\vec{r}:\mathbb{R}\to\mathbb{R}^n$, where the input $t$ is a [scalar] and the output $\vec{r}(t)$ is an [$n$-dimensional vector].

Q: In $\vec{r}:\mathbb{R}\to\mathbb{R}^n$, what do the domain and codomain represent geometrically?
A: The domain $\mathbb{R}$ is a one-dimensional parameter line, typically interpreted as time, while the codomain $\mathbb{R}^n$ is the ambient space (usually the plane when $n=2$ or 3D space when $n=3$) in which the output vectors live. Varying the single input $t$ sweeps out a curve in the higher-dimensional codomain.

## 3.2 Component Form

C: In three dimensions, a vector-valued function in component form is written $\vec{r}(t) = \langle f(t), g(t), h(t)\rangle$, where $f$, $g$, and $h$ are the [component functions] of $\vec{r}$.

Q: Why is the component form $\vec{r}(t) = \langle f(t), g(t), h(t)\rangle$ so useful for analyzing vector functions?
A: It reduces questions about a single vector function to three independent questions about ordinary scalar functions, so limits, derivatives, and integrals can each be handled component-by-component using single-variable calculus. This lets us reuse all tools from Calculus I without inventing a new theory of differentiation for vectors.

C: The component functions of $\vec{r}(t) = \langle t, t^2, t^3\rangle$ are $f(t) = t$, $g(t) = [t^2]$, and $h(t) = [t^3]$.

## 3.3 Space Curves as Images

C: The [space curve] traced by $\vec{r}(t)$ is the set of points $\{\vec{r}(t) : t \in I\}$ obtained as the tip of $\vec{r}(t)$ moves while $t$ ranges over the domain $I$.

Q: What is the distinction between a vector-valued function and the space curve it defines?
A: The function $\vec{r}(t)$ is a rule assigning a vector to each scalar $t$, carrying information about how the curve is traced (direction, speed, repetition). The space curve is only the image — the set of points in $\mathbb{R}^n$ visited — so many different vector functions can parametrize the same curve with different speeds or directions.

Q: Can two different vector functions produce the same space curve? Give an example.
A: Yes. $\vec{r}_1(t) = \langle \cos t, \sin t\rangle$ and $\vec{r}_2(t) = \langle \cos 2t, \sin 2t\rangle$ both trace the unit circle, but $\vec{r}_2$ traverses it twice as fast. The underlying set of points (the image) is identical, but the parametrizations differ.

## 3.4 Parametrizing Common Curves

C: A circle of radius $r$ centered at the origin in the $xy$-plane can be parametrized as $\vec{r}(t) = \langle [r\cos t], [r\sin t]\rangle$ for $t \in [0, 2\pi]$, where $r$ is the radius and $t$ is the angle from the positive $x$-axis.

Q: Why does $\vec{r}(t) = \langle r\cos t, r\sin t\rangle$ trace a circle of radius $r$ exactly once as $t$ goes from $0$ to $2\pi$?
A: Because $x^2 + y^2 = r^2\cos^2 t + r^2\sin^2 t = r^2$, every point lies on the circle, and the angle $t$ sweeps continuously from $0$ to $2\pi$ without repetition. The parametrization is one-to-one on $[0, 2\pi)$.

C: A circular [helix] of radius $r$ rising with pitch $c$ along the $z$-axis is parametrized as $\vec{r}(t) = \langle r\cos t, r\sin t, ct\rangle$, where $r$ is the radius of the circular projection and $c$ controls the vertical rise per unit $t$.

Q: What is the parametrization of the line segment from point $\vec{P}$ to point $\vec{Q}$, and why does it work?
A: $\vec{r}(t) = (1 - t)\vec{P} + t\vec{Q}$ for $t \in [0, 1]$. At $t = 0$ we get $\vec{P}$, at $t = 1$ we get $\vec{Q}$, and for intermediate $t$ we get a convex combination, which geometrically is a point on the straight segment between them.

## 3.5 Limits of Vector Functions

C: The limit of a vector function is taken [component-wise]: $\lim_{t \to a} \vec{r}(t) = \langle \lim_{t \to a} f(t), \lim_{t \to a} g(t), \lim_{t \to a} h(t)\rangle$, provided each component limit exists.

Q: Why is it legitimate to compute the limit of a vector function one component at a time?
A: A sequence of vectors converges in $\mathbb{R}^n$ if and only if each coordinate sequence converges in $\mathbb{R}$, because the Euclidean distance between vectors is controlled by the distances between corresponding components. This theorem reduces vector limits to familiar scalar limits.

## 3.6 Continuity of a Vector Function

C: A vector function $\vec{r}(t)$ is continuous at $t = a$ if and only if each of its [component functions] is continuous at $t = a$.

Q: Why does component-wise continuity imply continuity of the vector function itself?
A: If every component function satisfies $\lim_{t\to a} f_i(t) = f_i(a)$, then $\lim_{t\to a}\vec{r}(t) = \vec{r}(a)$ by the component-wise limit theorem. Geometrically, the tip of $\vec{r}(t)$ approaches $\vec{r}(a)$ smoothly with no jumps in any coordinate.

## 3.7 Derivative of a Vector Function

C: The derivative of $\vec{r}(t) = \langle f(t), g(t), h(t)\rangle$ is computed [component-wise]: $\vec{r}\,'(t) = \langle f'(t), g'(t), h'(t)\rangle$, where each prime denotes ordinary single-variable differentiation.

Q: Why is component-wise differentiation of a vector function valid, rather than something requiring a new definition?
A: Starting from the limit definition $\vec{r}\,'(t) = \lim_{h\to 0} \frac{\vec{r}(t+h) - \vec{r}(t)}{h}$ and applying the component-wise limit rule, each coordinate of the difference quotient becomes an ordinary scalar difference quotient. The resulting derivative is therefore the vector whose components are the derivatives of the original components.

## 3.8 Geometric Meaning of the Derivative

Q: Before we state the geometric meaning — predict: if $\vec{r}(t)$ traces a curve in space, what should the direction of $\vec{r}\,'(t)$ be?
A: It should point along the curve at the point $\vec{r}(t)$, because the derivative is a limit of secant vectors $\vec{r}(t+h) - \vec{r}(t)$ that shrink toward the curve's direction of travel.

C: At any point where $\vec{r}\,'(t) \neq \vec{0}$, the derivative $\vec{r}\,'(t)$ is [tangent] to the curve at $\vec{r}(t)$ and points in the direction of increasing $t$.

Q: Why does the derivative $\vec{r}\,'(t)$ give a tangent vector to the curve?
A: The difference quotient $\frac{\vec{r}(t+h) - \vec{r}(t)}{h}$ is a secant vector scaled by $1/h$, and as $h \to 0$ this secant rotates into the curve's direction of motion at $\vec{r}(t)$. Its limit therefore lies along the tangent line, with orientation matching increasing $t$.

## 3.9 Unit Tangent Vector

C: The [unit tangent vector] to a smooth curve at parameter $t$ is $\vec{T}(t) = \dfrac{\vec{r}\,'(t)}{|\vec{r}\,'(t)|}$, where $\vec{r}\,'(t)$ is the velocity vector and $|\vec{r}\,'(t)|$ is its magnitude.

Q: Why do we normalize $\vec{r}\,'(t)$ to get $\vec{T}(t)$ instead of just using $\vec{r}\,'(t)$ itself?
A: The tangent direction to a curve depends only on the geometry of the curve, not on how fast it is traced. Dividing by $|\vec{r}\,'(t)|$ strips away the parametrization's speed, leaving a unit vector that depends only on the curve's shape at that point.

Q: Why does $\vec{T}(t)$ fail to exist where $\vec{r}\,'(t) = \vec{0}$?
A: Dividing by zero is undefined, and geometrically the curve may have a cusp or momentarily stop, so no well-defined tangent direction exists. Points where $\vec{r}\,'(t) = \vec{0}$ are called singular points of the parametrization.

## 3.10 Differentiation Rules for Vector Functions

C: Sum rule: $\dfrac{d}{dt}[\vec{u}(t) + \vec{v}(t)] = [\vec{u}\,'(t) + \vec{v}\,'(t)]$, where $\vec{u}$ and $\vec{v}$ are differentiable vector functions of $t$.

C: Scalar multiple rule: $\dfrac{d}{dt}[c\,\vec{u}(t)] = [c\,\vec{u}\,'(t)]$ for any constant scalar $c$.

C: Scalar-times-vector product rule: $\dfrac{d}{dt}[f(t)\vec{u}(t)] = [f'(t)\vec{u}(t) + f(t)\vec{u}\,'(t)]$, where $f$ is a scalar function and $\vec{u}$ is a vector function.

C: Dot product rule: $\dfrac{d}{dt}[\vec{u}(t)\cdot\vec{v}(t)] = [\vec{u}\,'(t)\cdot\vec{v}(t) + \vec{u}(t)\cdot\vec{v}\,'(t)]$.

C: Cross product rule: $\dfrac{d}{dt}[\vec{u}(t)\times\vec{v}(t)] = [\vec{u}\,'(t)\times\vec{v}(t) + \vec{u}(t)\times\vec{v}\,'(t)]$, where order must be preserved because the cross product is not commutative.

C: Chain rule: $\dfrac{d}{dt}\vec{u}(f(t)) = [\vec{u}\,'(f(t))\,f'(t)]$, where $f$ is a differentiable scalar function of $t$.

## 3.11 Why the Dot-Product Rule Has a Familiar Form

Q: Why does the dot-product rule $\frac{d}{dt}(\vec{u}\cdot\vec{v}) = \vec{u}\,'\cdot\vec{v} + \vec{u}\cdot\vec{v}\,'$ look exactly like the ordinary product rule?
A: Because the dot product $\vec{u}\cdot\vec{v} = \sum_i u_i v_i$ is a sum of products of scalar components, applying the single-variable product rule to each term and regrouping yields $\sum_i (u_i' v_i + u_i v_i') = \vec{u}\,'\cdot\vec{v} + \vec{u}\cdot\vec{v}\,'$. The vector rule is really the scalar product rule applied coordinate-by-coordinate.

Q: Why must the cross-product rule preserve the order $\vec{u}\,' \times \vec{v} + \vec{u} \times \vec{v}\,'$ rather than allowing factors to be swapped?
A: Because the cross product is anti-commutative ($\vec{a}\times\vec{b} = -\vec{b}\times\vec{a}$), reversing factors changes the sign. The derivation via components shows each differentiated factor must stay in its original position to produce the correct signed result.

## 3.12 Derivative of a Constant-Magnitude Vector

Q: If $|\vec{r}(t)| = c$ for all $t$ (a constant), what can you say about $\vec{r}(t)$ and $\vec{r}\,'(t)$, and why?
A: They are perpendicular for every $t$: $\vec{r}(t)\cdot\vec{r}\,'(t) = 0$. Differentiating $\vec{r}\cdot\vec{r} = c^2$ using the dot-product rule gives $2\vec{r}\cdot\vec{r}\,' = 0$, so the vectors are orthogonal.

C: If a vector function $\vec{r}(t)$ has constant magnitude, then its derivative $\vec{r}\,'(t)$ is [perpendicular] to $\vec{r}(t)$ at every $t$.

Q: Why is the result "constant-magnitude vector is perpendicular to its derivative" useful for the unit tangent vector $\vec{T}(t)$?
A: Since $|\vec{T}(t)| = 1$ is constant, its derivative $\vec{T}\,'(t)$ is perpendicular to $\vec{T}(t)$. This is why the principal normal direction $\vec{N}(t) = \vec{T}\,'(t)/|\vec{T}\,'(t)|$ is guaranteed to be orthogonal to the tangent direction.

## 3.13 Integration of Vector Functions

C: The indefinite integral of a vector function is computed [component-wise]: $\int \vec{r}(t)\,dt = \langle \int f(t)\,dt, \int g(t)\,dt, \int h(t)\,dt\rangle + \vec{C}$, where $\vec{C}$ is a constant vector of integration.

Q: Why does integrating a vector function produce a vector constant of integration $\vec{C}$ rather than a scalar one?
A: Each component integral contributes its own scalar constant $C_i$, and collecting these into a single object gives a constant vector $\vec{C} = \langle C_1, C_2, C_3\rangle$. Geometrically, $\vec{C}$ encodes the unknown initial position or offset in each coordinate direction.

C: The definite integral $\int_a^b \vec{r}(t)\,dt$ is the vector $\langle \int_a^b f(t)\,dt, \int_a^b g(t)\,dt, \int_a^b h(t)\,dt\rangle$, where $f$, $g$, $h$ are the [components] of $\vec{r}$.

## 3.14 Initial Value Problems for Vector Functions

Q: In a vector initial value problem, why do you typically need TWO initial conditions to recover position from acceleration?
A: Integrating $\vec{a}(t)$ once gives $\vec{v}(t)$ up to a vector constant (so you need $\vec{v}(t_0)$), and integrating again gives $\vec{r}(t)$ up to another vector constant (so you need $\vec{r}(t_0)$). Each integration introduces an unknown vector that must be pinned down by a separate initial condition.

C: To recover $\vec{r}(t)$ from acceleration $\vec{a}(t)$, integrate twice: first $\vec{v}(t) = \int \vec{a}(t)\,dt + \vec{v}_0$, then $\vec{r}(t) = \int \vec{v}(t)\,dt + \vec{r}_0$, where $\vec{v}_0 = \vec{v}(t_0)$ is the [initial velocity] and $\vec{r}_0 = \vec{r}(t_0)$ is the [initial position].

## 3.15 Position, Velocity, and Acceleration

C: If $\vec{r}(t)$ is the position of a particle in $\mathbb{R}^3$, then its [velocity] is $\vec{v}(t) = \vec{r}\,'(t)$ and its [acceleration] is $\vec{a}(t) = \vec{v}\,'(t) = \vec{r}\,''(t)$.

Q: Why is velocity a vector quantity while speed is scalar, and how are they related?
A: Velocity $\vec{v}(t) = \vec{r}\,'(t)$ carries both magnitude and direction, describing how fast and in what direction the particle moves. Speed is the magnitude $|\vec{v}(t)|$, discarding directional information. Two particles can have the same speed but very different velocities.

## 3.16 Speed

C: The [speed] of a particle with position $\vec{r}(t)$ is $|\vec{v}(t)| = |\vec{r}\,'(t)| = \sqrt{f'(t)^2 + g'(t)^2 + h'(t)^2}$, where $f$, $g$, $h$ are the components of $\vec{r}$.

Q: Why is speed the magnitude of the velocity rather than the magnitude of the position vector?
A: Position magnitude $|\vec{r}(t)|$ measures distance from the origin, which has nothing to do with how fast the particle is moving. Speed measures how quickly arc length accumulates along the path, and $|\vec{r}\,'(t)|$ is exactly $\frac{ds}{dt}$, the rate of change of arc length with respect to $t$.

## 3.17 Projectile Motion in Vector Form

Q: In projectile motion near Earth's surface, why is the acceleration vector $\vec{a}(t) = \langle 0, -g, 0\rangle$ (with $y$ vertical), and why is it constant?
A: Gravity is the only force (ignoring air resistance), it acts purely downward, and its magnitude $g \approx 9.8\ \text{m/s}^2$ is essentially uniform near the surface. With $y$-axis vertical, the acceleration has zero horizontal components and a constant negative $y$-component.

C: The position of a projectile launched from $\vec{r}_0$ with initial velocity $\vec{v}_0$ under gravity alone is $\vec{r}(t) = \vec{r}_0 + \vec{v}_0 t + \frac{1}{2}\langle 0, -g, 0\rangle t^2$, where $g$ is the magnitude of [gravitational acceleration].

Q: Why does projectile motion decompose so cleanly into independent horizontal and vertical motions?
A: Because acceleration has no horizontal component, the horizontal velocity is constant and horizontal position is linear in $t$. The vertical component evolves independently under constant gravity, giving a parabola in the vertical coordinate. The two motions do not couple, which is a direct consequence of component-wise integration.

## 3.18 Kepler's Laws

C: Kepler's [first law] states that planets move in ellipses with the Sun at one focus.

C: Kepler's [second law] states that the line from the Sun to a planet sweeps out equal areas in equal times, which is equivalent to conservation of angular momentum.

C: Kepler's [third law] states that $T^2 \propto a^3$, where $T$ is the orbital period and $a$ is the semi-major axis of the orbit.

Q: Why is Kepler's second law ("equal areas in equal times") a statement about a constant-magnitude vector function?
A: The swept area rate is $\frac{dA}{dt} = \frac{1}{2}|\vec{r}\times\vec{v}|$, which is half the magnitude of angular momentum per unit mass. For a central gravitational force, $\vec{r}\times\vec{v}$ is conserved, so its magnitude is constant. This is an application of vector-function calculus: differentiating $\vec{r}\times\vec{v}$ using the cross-product rule and using $\vec{a}\parallel\vec{r}$ gives zero.

Q: Why does the derivative of $\vec{r}\times\vec{v}$ vanish for a planet orbiting under gravity?
A: By the cross-product rule, $\frac{d}{dt}(\vec{r}\times\vec{v}) = \vec{v}\times\vec{v} + \vec{r}\times\vec{a}$. The first term is zero because the cross product of any vector with itself vanishes, and $\vec{a}$ is parallel to $\vec{r}$ (central force along the line to the Sun), so $\vec{r}\times\vec{a} = \vec{0}$. Hence $\vec{r}\times\vec{v}$ is constant.

## 3.19 IVP from Constant Acceleration

P: A particle has acceleration $\vec{a}(t) = \langle 0, -g, 0\rangle$, initial velocity $\vec{v}(0) = \vec{v}_0 = \langle v_{0x}, v_{0y}, v_{0z}\rangle$, and initial position $\vec{r}(0) = \vec{0}$. Find the position vector $\vec{r}(t)$.

S:
**IDENTIFY**: Vector initial value problem — recover position from constant acceleration and two initial conditions. Here $g > 0$ is the magnitude of gravitational acceleration, $\vec{v}_0$ is the given initial velocity vector, and the particle starts at the origin.

**PLAN**:
- Integrate $\vec{a}(t)$ once component-wise to get velocity, using $\vec{v}(0) = \vec{v}_0$ to fix the constant vector.
- Integrate $\vec{v}(t)$ component-wise to get position, using $\vec{r}(0) = \vec{0}$ to fix the second constant vector.
- Write the answer as a single vector equation.

**EXECUTE**:
1. $\vec{v}(t) = \int \vec{a}(t)\,dt + \vec{C}_1 = \langle 0, -gt, 0\rangle + \vec{C}_1$.
2. Apply $\vec{v}(0) = \vec{v}_0$: $\langle 0, 0, 0\rangle + \vec{C}_1 = \vec{v}_0$, so $\vec{C}_1 = \vec{v}_0$. Therefore $\vec{v}(t) = \vec{v}_0 + \langle 0, -gt, 0\rangle$.
3. $\vec{r}(t) = \int \vec{v}(t)\,dt + \vec{C}_2 = \vec{v}_0 t + \langle 0, -\tfrac{1}{2}gt^2, 0\rangle + \vec{C}_2$.
4. Apply $\vec{r}(0) = \vec{0}$: $\vec{C}_2 = \vec{0}$.
5. Final answer: $\vec{r}(t) = \vec{v}_0 t + \langle 0, -\tfrac{1}{2}gt^2, 0\rangle = \langle v_{0x}t,\ v_{0y}t - \tfrac{1}{2}gt^2,\ v_{0z}t\rangle$.

**EVALUATE**:
- At $t = 0$: $\vec{r}(0) = \vec{0}$ ✓ and $\vec{v}(0) = \vec{v}_0$ ✓.
- Differentiate twice: $\vec{r}\,''(t) = \langle 0, -g, 0\rangle = \vec{a}(t)$ ✓.
- Horizontal components are linear in $t$ (no horizontal force), vertical component is the familiar $v_{0y}t - \tfrac{1}{2}gt^2$ from 1D kinematics. Units check: $[v_0 t] = \text{m}$ and $[g t^2] = \text{m}$.

## 3.20 Unit Tangent at a Specific Point

P: Find the unit tangent vector $\vec{T}(1)$ to the curve $\vec{r}(t) = \langle t, t^2, t^3\rangle$ at $t = 1$.

S:
**IDENTIFY**: Unit tangent vector at a specific parameter value. Need $\vec{T}(t) = \vec{r}\,'(t)/|\vec{r}\,'(t)|$ evaluated at $t = 1$, where $\vec{r}\,'(t)$ is the velocity vector (tangent direction) and $|\vec{r}\,'(t)|$ is its magnitude (speed).

**PLAN**:
- Differentiate $\vec{r}(t)$ component-wise to get $\vec{r}\,'(t)$.
- Evaluate $\vec{r}\,'(1)$.
- Compute its magnitude $|\vec{r}\,'(1)|$.
- Divide to obtain the unit tangent vector.

**EXECUTE**:
1. $\vec{r}\,'(t) = \langle 1, 2t, 3t^2\rangle$.
2. $\vec{r}\,'(1) = \langle 1, 2, 3\rangle$.
3. $|\vec{r}\,'(1)| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{1 + 4 + 9} = \sqrt{14}$.
4. $\vec{T}(1) = \dfrac{\langle 1, 2, 3\rangle}{\sqrt{14}} = \left\langle \dfrac{1}{\sqrt{14}}, \dfrac{2}{\sqrt{14}}, \dfrac{3}{\sqrt{14}}\right\rangle$.

**EVALUATE**:
- Check magnitude: $\sqrt{(1/\sqrt{14})^2 + (2/\sqrt{14})^2 + (3/\sqrt{14})^2} = \sqrt{14/14} = 1$ ✓.
- Direction: positive in all three components, consistent with $\vec{r}(t) = \langle t, t^2, t^3\rangle$ increasing in each coordinate near $t = 1$.
- Since $\vec{r}\,'(1) \neq \vec{0}$, the curve is smooth at this point and the unit tangent is well-defined.
