+++
order = 13
tags = ["math", "multivariable-calculus", "vector-fields", "line-integrals", "work", "flux"]
+++

# Multivariable Calculus — Vector Fields and Line Integrals

## 13.1 Vector Fields

Q: Why do we need vector fields in addition to scalar fields?
A: Many physical quantities have both magnitude and direction at every point — think of wind velocity, gravitational pull, or electric force. A scalar field assigns a number to each point, but a vector field assigns a full vector, capturing the directional structure needed to model flow, force, and circulation.

C: A [vector field] on $\mathbb{R}^n$ is a function $\vec{F}: \mathbb{R}^n \to \mathbb{R}^n$ that assigns a vector to each point in its domain.

C: In 2D, a vector field is written $\vec{F}(x,y) = \langle P(x,y), Q(x,y)\rangle$, where $P$ and $Q$ are the [component functions] of $\vec{F}$.

C: In 3D, a vector field is written $\vec{F}(x,y,z) = \langle P, Q, R\rangle$, where $P$, $Q$, $R$ are scalar functions of $(x,y,z)$ giving the $[\hat{i}, \hat{j}, \hat{k}]$ components of $\vec{F}$.

Q: What does it mean for a vector field to be continuous?
A: A vector field $\vec{F} = \langle P, Q, R\rangle$ is continuous at a point exactly when each of its component functions $P$, $Q$, $R$ is continuous there. Continuity of the field reduces to continuity of its scalar pieces.

C: A vector field $\vec{F}$ is called a [gradient field] (or conservative field) if there exists a scalar function $f$ such that $\vec{F} = \nabla f$; the function $f$ is a potential for $\vec{F}$.

Q: Why are gradient fields especially important?
A: Gradient fields package the geometry of a scalar potential $f$ into a vector field $\nabla f$ that points in the direction of steepest increase of $f$. This structure makes work integrals path-independent and underlies conservative forces like gravity and electrostatics.

C: The gravitational field of a point mass $M$ at the origin is $\vec{F}(\vec{r}) = -\dfrac{GM}{|\vec{r}|^3}\vec{r}$, where $\vec{r}$ is the position vector of the field point and $G$ is the [gravitational constant].

Q: How do you sketch a vector field by hand?
A: Pick a grid of sample points, evaluate $\vec{F}$ at each one, and draw a small arrow at each point whose direction matches $\vec{F}$ and whose length is proportional to $|\vec{F}|$. Arrow lengths are usually rescaled uniformly so the picture is readable.

Q: What distinguishes a velocity field from a force field conceptually?
A: A velocity field $\vec{v}(\vec{r})$ gives the velocity of a fluid particle passing through each point, describing motion. A force field $\vec{F}(\vec{r})$ gives the force experienced by a test object at each point, describing potential action on a particle not yet moving.

## 13.2 Line Integrals of Scalar Functions

Q: Why generalize the single-variable integral $\int_a^b f(x)\,dx$ to a line integral along a curve?
A: In the plane or space, we often want to sum a scalar quantity along a curved path rather than along a straight $x$-axis — for example, total mass of a wire of variable density, or average temperature along a hiking trail. The line integral replaces $dx$ with the curve's own arc length element $ds$ to respect the geometry of the path.

C: The line integral of a scalar function $f$ along a curve $C$ is written $[\int_C f\,ds]$, where $ds$ is the arc length element along $C$.

C: If $C$ is parametrized by $\vec{r}(t)$ for $t \in [a,b]$, then $\int_C f\,ds = \int_a^b f(\vec{r}(t))\,[|\vec{r}'(t)|]\,dt$, since $ds = |\vec{r}'(t)|\,dt$.

Q: What is the geometric interpretation of $\int_C f\,ds$ when $f \geq 0$ is defined on a plane curve $C$?
A: It equals the area of the "curtain" whose base is $C$ in the $xy$-plane and whose height above each point of $C$ is $f(x,y)$. The curve acts as a curved base, and $f$ gives the height of a vertical fence erected along it.

Q: What does $\int_C 1\,ds$ compute?
A: The total arc length of the curve $C$. With $f \equiv 1$, the scalar line integral reduces to summing arc length elements, recovering the length formula $\int_a^b |\vec{r}'(t)|\,dt$.

Q: If $\rho(x,y,z)$ is the linear mass density of a wire shaped like curve $C$, what does $\int_C \rho\,ds$ give?
A: The total mass of the wire. The line integral sums infinitesimal masses $\rho\,ds$ (density times arc length element) over the entire curve.

## 13.3 Line Integrals of Vector Fields

Q: Why do we define a separate line integral for vector fields instead of reusing the scalar line integral?
A: A vector field has direction, so how much it "contributes" along a curve depends on alignment with the curve's tangent. We want an integral that measures the component of $\vec{F}$ along the path, not just its magnitude — this is what captures physical work and circulation.

C: The line integral of a vector field $\vec{F}$ along an oriented curve $C$ is $[\int_C \vec{F}\cdot d\vec{r}]$, interpreted as the accumulated tangential component of $\vec{F}$ along $C$.

C: If $C$ is parametrized by $\vec{r}(t)$ for $t \in [a,b]$, then $\int_C \vec{F}\cdot d\vec{r} = \int_a^b \vec{F}(\vec{r}(t))\cdot [\vec{r}'(t)]\,dt$, where $\vec{r}'(t)$ is the velocity vector along the curve.

Q: How are $\int_C \vec{F}\cdot d\vec{r}$ and $\int_C (\vec{F}\cdot\hat{T})\,ds$ related?
A: They are equal. Since $\hat{T} = \vec{r}'(t)/|\vec{r}'(t)|$ and $ds = |\vec{r}'(t)|\,dt$, the product $\hat{T}\,ds = \vec{r}'(t)\,dt = d\vec{r}$, so the vector line integral is exactly the scalar line integral of the tangential component $\vec{F}\cdot\hat{T}$.

Q: Physically, what does $\int_C \vec{F}\cdot d\vec{r}$ represent when $\vec{F}$ is a force field?
A: The work done by the force $\vec{F}$ on a particle moving along $C$. Only the component of force along the direction of motion performs work; the dot product $\vec{F}\cdot d\vec{r}$ extracts exactly that component at each infinitesimal step.

Q: Why can $\int_C \vec{F}\cdot d\vec{r}$ be negative?
A: The integrand $\vec{F}\cdot\vec{r}'(t)$ is negative wherever the field opposes the direction of motion. If the force pushes against the particle more than with it along the path, the net work is negative — the particle has done work against the field.

## 13.4 Work Done by a Force Field

C: The work done by a force field $\vec{F}$ on a particle moving along an oriented curve $C$ is $W = [\int_C \vec{F}\cdot d\vec{r}]$.

Q: Why does the straight-line formula $W = \vec{F}\cdot\vec{d}$ fail for curved paths or variable forces?
A: The elementary formula assumes a constant force and a straight displacement $\vec{d}$. On a curved path with a position-dependent force, both the force vector and the direction of motion change continuously, so work must be summed through an integral of $\vec{F}\cdot d\vec{r}$ over infinitesimal displacements.

Q: In the work integral, why do we dot $\vec{F}$ with $d\vec{r}$ rather than multiply $|\vec{F}|$ by $ds$?
A: Only the component of $\vec{F}$ parallel to motion contributes to work; any perpendicular component does none. The dot product $\vec{F}\cdot d\vec{r}$ automatically projects the force onto the tangent direction, while $|\vec{F}|\,ds$ would overcount by ignoring direction.

Q: If $\vec{F}$ is perpendicular to the curve $C$ at every point, what is the work done?
A: Zero. At every point $\vec{F}\cdot\vec{r}'(t) = 0$, so the integrand vanishes along the entire path — a force that only pushes sideways to the motion performs no work, like the normal force on a block sliding horizontally.

P: Compute the work done by the force field $\vec{F}(x,y) = \langle y, -x\rangle$ on a particle moving along the upper semicircle $C$ of radius $1$ from $(1,0)$ to $(-1,0)$.

S:
**IDENTIFY**: Work integral of a 2D vector field along a parametrized curve; compute $W = \int_C \vec{F}\cdot d\vec{r}$.

**PLAN**:
- Parametrize the upper semicircle: $\vec{r}(t) = \langle \cos t, \sin t\rangle$ for $t \in [0, \pi]$.
- Compute $\vec{r}'(t)$ (velocity vector).
- Evaluate $\vec{F}(\vec{r}(t))$ by substitution.
- Form $\vec{F}\cdot\vec{r}'(t)$ and integrate from $0$ to $\pi$.

**EXECUTE**:
1. $\vec{r}'(t) = \langle -\sin t, \cos t\rangle$.
2. $\vec{F}(\vec{r}(t)) = \langle \sin t, -\cos t\rangle$ (using $x=\cos t$, $y=\sin t$).
3. Dot product: $\vec{F}\cdot\vec{r}'(t) = (\sin t)(-\sin t) + (-\cos t)(\cos t) = -\sin^2 t - \cos^2 t = -1$.
4. $W = \int_0^{\pi} (-1)\,dt = -\pi$.

**EVALUATE**:
- The field $\langle y, -x\rangle$ rotates clockwise, while the parametrization moves counterclockwise along the upper semicircle, so $\vec{F}$ opposes motion at every point — a negative answer is expected.
- Magnitude $\pi$ equals the arc length of the semicircle, consistent with $\vec{F}\cdot\hat{T} = -1$ being constant along $C$.

## 13.5 Orientation and Parametrization

C: An [orientation] of a curve $C$ is a choice of direction of travel along it; a parametrization $\vec{r}(t)$ induces an orientation via increasing $t$.

Q: Why does $\int_C \vec{F}\cdot d\vec{r}$ depend on orientation but $\int_C f\,ds$ does not?
A: Reversing direction flips the sign of the tangent vector $\vec{r}'(t)$, which flips the sign of $\vec{F}\cdot d\vec{r}$ at every point. The scalar integrand $f\,ds$ uses $ds = |\vec{r}'(t)|\,dt \geq 0$, which has no direction, so its value is unchanged.

C: If $-C$ denotes the curve $C$ traversed in the opposite orientation, then $\int_{-C} \vec{F}\cdot d\vec{r} = [-\int_C \vec{F}\cdot d\vec{r}]$.

C: For scalar line integrals, reversing orientation leaves the value unchanged: $\int_{-C} f\,ds = [\int_C f\,ds]$.

Q: Why is the line integral of a vector field independent of the specific parametrization used (up to sign)?
A: Any two smooth parametrizations of the same oriented curve are related by a strictly increasing change of variable, under which the dot-product integral transforms correctly and gives the same value. The integral depends only on the geometric curve and its orientation, not on the speed or labeling of points.

Q: If you reparametrize $C$ by arc length, does $\int_C \vec{F}\cdot d\vec{r}$ change?
A: No. Arc-length reparametrization preserves orientation and traces the same point set, so the integral evaluates to the same number. It simply replaces $\vec{r}'(t)$ with the unit tangent $\hat{T}$ and $dt$ with $ds$, turning the integrand into $\vec{F}\cdot\hat{T}\,ds$.

## 13.6 Flux Across a Plane Curve

Q: Why do we want a "flux across a curve" integral distinct from the work integral?
A: Work measures how much a field pushes along a curve (tangential contribution), but many problems ask how much of the field crosses the curve instead — for example, the rate at which fluid flows across a boundary. Flux is computed with the normal component of $\vec{F}$, not the tangential one.

C: Let $C$ be a smooth plane curve with unit outward normal $\hat{n}$. The [flux] of $\vec{F}$ across $C$ is $\int_C \vec{F}\cdot\hat{n}\,ds$, where $\hat{n}$ is the unit vector perpendicular to $C$ pointing in the chosen outward direction.

C: For a plane curve with unit tangent $\hat{T} = \langle T_x, T_y\rangle$, a consistent choice of outward unit normal is $\hat{n} = [\langle T_y, -T_x\rangle]$ (rotate $\hat{T}$ by $90°$ clockwise).

C: If $C$ is parametrized by $\vec{r}(t) = \langle x(t), y(t)\rangle$ and $\vec{F} = \langle P, Q\rangle$, then the flux integral becomes $\int_C \vec{F}\cdot\hat{n}\,ds = \int_a^b [P\,y'(t) - Q\,x'(t)]\,dt$.

Q: Physically, what does flux measure when $\vec{F}$ is the velocity field of a 2D fluid?
A: It measures the net rate at which fluid crosses the curve $C$, in units of area per unit time. Positive flux means net outward flow (along $\hat{n}$); negative flux means net inward flow.

Q: Why does flux change sign if you flip the choice of $\hat{n}$?
A: Flux is built from $\vec{F}\cdot\hat{n}$, so reversing $\hat{n}$ to $-\hat{n}$ multiplies the integrand by $-1$ everywhere. "Outward" is a convention; choosing the opposite normal simply reports the same physical flow with the opposite sign.

## 13.7 Differential Form of Line Integrals

Q: Why rewrite $\int_C \vec{F}\cdot d\vec{r}$ as $\int_C P\,dx + Q\,dy + R\,dz$?
A: Expanding the dot product in coordinates exposes the integral as a sum of contributions from each coordinate direction, matching the way physicists and differential-forms notation encode line integrals. It also makes it easy to read off component functions when $\vec{F}$ is given implicitly by a differential expression.

C: For $\vec{F} = \langle P, Q, R\rangle$ and $d\vec{r} = \langle dx, dy, dz\rangle$, the dot product gives $\vec{F}\cdot d\vec{r} = [P\,dx + Q\,dy + R\,dz]$, where $P$, $Q$, $R$ depend on $(x,y,z)$.

C: In differential form, $\int_C \vec{F}\cdot d\vec{r} = \int_C P\,dx + Q\,dy + R\,dz$, and along a parametrization with parameter $t$, each $dx$, $dy$, $dz$ is replaced by $[x'(t)\,dt, y'(t)\,dt, z'(t)\,dt]$ respectively.

Q: Given the differential-form integral $\int_C x^2\,dx + xy\,dy$, what is the underlying vector field $\vec{F}$?
A: The vector field is $\vec{F}(x,y) = \langle x^2, xy\rangle$. The coefficient of $dx$ is the $P$-component, and the coefficient of $dy$ is the $Q$-component.

Q: Why is the differential form $P\,dx + Q\,dy + R\,dz$ only meaningful when paired with an oriented curve?
A: Each term $P\,dx$ etc. is a signed contribution: $dx$ records the change in $x$ along the curve, which flips sign if the orientation reverses. Without a choice of direction, the symbols have no determinate value; the orientation tells us which way $x$, $y$, $z$ are changing.
