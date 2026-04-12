+++
order = 15
tags = ["math", "multivariable-calculus", "surface-integrals", "stokes-theorem", "divergence-theorem", "flux", "curl"]
+++

# Multivariable Calculus — Surface Integrals, Stokes' and Divergence Theorems

## 15.1 Parametric Surfaces

Q: Why do we need a vector function of two parameters to describe a surface?
A: A surface is a 2D object embedded in 3D space, so we need two independent parameters to sweep across it, just as a curve needs one parameter. The output is a 3D point, requiring a vector-valued function whose two inputs trace out every point on the surface.

C: A [parametric surface] is described by $\vec{r}(u,v) = \langle x(u,v), y(u,v), z(u,v)\rangle$, where $u$ and $v$ are parameters ranging over a domain $D$ in the $uv$-plane.

C: The partial derivative $\vec{r}_u = \dfrac{\partial \vec{r}}{\partial u}$ is the [tangent vector] to the curve obtained by fixing $v$ and varying $u$ on the surface.

C: Fixing one parameter of $\vec{r}(u,v)$ produces a [grid curve] on the surface, and $\vec{r}_u$, $\vec{r}_v$ are tangent vectors to these curves.

Q: Why is $\vec{r}_u \times \vec{r}_v$ normal to the surface at a point?
A: Both $\vec{r}_u$ and $\vec{r}_v$ lie in the tangent plane since they are tangent to grid curves on the surface. Their cross product is therefore perpendicular to every vector in that plane, making it normal to the surface at $\vec{r}(u,v)$.

C: A point $\vec{r}(u_0, v_0)$ on a surface is called [smooth] when $\vec{r}_u \times \vec{r}_v \neq \vec{0}$ there, so a unique tangent plane exists.

Q: What is the equation of the tangent plane to a smooth parametric surface at $\vec{r}(u_0, v_0)$?
A: It is the plane through $\vec{r}(u_0,v_0)$ with normal vector $\vec{n} = \vec{r}_u(u_0,v_0) \times \vec{r}_v(u_0,v_0)$. Any point $\vec{p}$ on the plane satisfies $\vec{n} \cdot (\vec{p} - \vec{r}(u_0,v_0)) = 0$.

## 15.2 Surface Area from a Parametrization

Q: Why does surface area involve $|\vec{r}_u \times \vec{r}_v|$?
A: A small rectangle $du\,dv$ in parameter space maps to a small patch on the surface approximated by the parallelogram spanned by $\vec{r}_u\,du$ and $\vec{r}_v\,dv$. The area of that parallelogram is $|\vec{r}_u \times \vec{r}_v|\,du\,dv$, so integrating this local area element gives total surface area.

C: The surface area of a smooth parametric surface $\vec{r}(u,v)$ over domain $D$ is $A(S) = \iint_D [|\vec{r}_u \times \vec{r}_v|]\,dA$, where $\vec{r}_u, \vec{r}_v$ are partial derivatives of $\vec{r}$.

C: The scalar [$|\vec{r}_u \times \vec{r}_v|\,dA$] is called the surface area element $dS$, representing infinitesimal area on $S$.

## 15.3 Surface Area for a Graph $z = f(x,y)$

Q: Why does the graph $z = f(x,y)$ have surface area $\iint_D \sqrt{1 + f_x^2 + f_y^2}\,dA$?
A: Parametrize the graph as $\vec{r}(x,y) = \langle x, y, f(x,y)\rangle$. Then $\vec{r}_x = \langle 1,0,f_x\rangle$ and $\vec{r}_y = \langle 0,1,f_y\rangle$, whose cross product is $\langle -f_x, -f_y, 1\rangle$ with magnitude $\sqrt{1+f_x^2+f_y^2}$. Integrating this gives the formula.

C: For a surface given as the graph $z = f(x,y)$ over region $D$, the area is $A(S) = \iint_D [\sqrt{1 + f_x^2 + f_y^2}]\,dA$, where $f_x, f_y$ are partial derivatives of $f$.

## 15.4 Surface Integrals of Scalar Functions

Q: Why do we define a surface integral $\iint_S f\,dS$ instead of just using a double integral?
A: A scalar function (like density or temperature) defined on a curved surface must be weighted by actual surface area, not parameter-domain area. The factor $|\vec{r}_u \times \vec{r}_v|$ converts a parameter rectangle into true surface area so the integral measures total quantity on $S$.

C: The surface integral of scalar function $f$ over parametric surface $S = \vec{r}(u,v)$ on $D$ is $\iint_S f\,dS = \iint_D f(\vec{r}(u,v))\,[|\vec{r}_u \times \vec{r}_v|]\,dA$.

C: If $\rho(x,y,z)$ is surface mass density, then the total mass of a thin shell $S$ is $m = \iint_S [\rho]\,dS$, where $dS$ is the surface area element.

Q: What does $\iint_S 1\,dS$ compute?
A: The surface area of $S$. Integrating the constant function $1$ over the surface just accumulates area elements, reducing to the surface-area formula.

## 15.5 Orientation

Q: Why must we choose an orientation before integrating a vector field over a surface?
A: A surface has two unit normal directions at each point, so flux ($\vec{F} \cdot \hat{n}$) could be positive or negative depending on which we pick. Choosing a consistent normal field across the whole surface fixes the sign of the answer and gives it physical meaning (e.g., outward flow).

C: An [orientable] surface admits a continuous choice of unit normal $\hat{n}$ over all of $S$.

C: For a closed surface (like a sphere), the standard convention is the [outward] pointing normal.

C: The [Möbius strip] is the classic example of a non-orientable surface, on which no continuous choice of unit normal exists.

Q: Why is the Möbius strip non-orientable?
A: Transporting a normal vector continuously once around the strip returns it pointing in the opposite direction, contradicting the requirement of a single-valued continuous normal field. No consistent "side" can be picked.

C: For a parametric surface, one orientation is $\hat{n} = \dfrac{\vec{r}_u \times \vec{r}_v}{|\vec{r}_u \times \vec{r}_v|}$; the [opposite] orientation is obtained by negating this or swapping $u$ and $v$.

## 15.6 Surface Integrals of Vector Fields (Flux)

Q: Why does flux through a surface measure $\vec{F} \cdot \hat{n}$ rather than $|\vec{F}|$?
A: Only the component of $\vec{F}$ perpendicular to the surface actually crosses it; the tangential component slides along. The dot product with $\hat{n}$ isolates the normal component, so $\vec{F} \cdot \hat{n}\,dS$ correctly measures the rate of flow through each patch.

C: The [flux] of a vector field $\vec{F}$ across oriented surface $S$ is $\iint_S \vec{F} \cdot d\vec{S} = \iint_S \vec{F} \cdot \hat{n}\,dS$, where $\hat{n}$ is the chosen unit normal.

C: If $\vec{F}$ is a fluid velocity field (m/s), then $\iint_S \vec{F} \cdot d\vec{S}$ gives the [volume of fluid per unit time] crossing $S$ in the direction of $\hat{n}$.

Q: What physically is the vector element $d\vec{S}$?
A: It is an infinitesimal area vector: its magnitude is the patch's area $dS$, and its direction is the chosen unit normal $\hat{n}$. So $d\vec{S} = \hat{n}\,dS$ encodes both size and orientation of the patch.

## 15.7 Computing Flux Through a Parametric Surface

Q: Why does $\iint_S \vec{F} \cdot d\vec{S} = \iint_D \vec{F}(\vec{r}(u,v)) \cdot (\vec{r}_u \times \vec{r}_v)\,dA$?
A: The unit normal is $\hat{n} = (\vec{r}_u \times \vec{r}_v)/|\vec{r}_u \times \vec{r}_v|$ and $dS = |\vec{r}_u \times \vec{r}_v|\,dA$, so the magnitudes cancel when combined. The result is simply $\vec{F}$ dotted with the unnormalized normal $\vec{r}_u \times \vec{r}_v$, integrated over the parameter domain $D$.

C: For parametric surface $\vec{r}(u,v)$ on $D$ with orientation from $\vec{r}_u\times\vec{r}_v$, flux is $\iint_S \vec{F}\cdot d\vec{S} = \iint_D [\vec{F}(\vec{r}(u,v)) \cdot (\vec{r}_u\times\vec{r}_v)]\,dA$.

P: Compute the flux of $\vec{F} = \langle x, y, z\rangle$ outward through the upper hemisphere $S: x^2+y^2+z^2 = 1$, $z \geq 0$.

S:
**IDENTIFY**: Flux integral $\iint_S \vec{F}\cdot d\vec{S}$ through a smooth parametric surface with specified orientation.

**PLAN**:
- Parametrize the hemisphere with spherical coordinates: $\vec{r}(\phi,\theta) = \langle \sin\phi\cos\theta, \sin\phi\sin\theta, \cos\phi\rangle$, $\phi\in[0,\pi/2]$, $\theta\in[0,2\pi]$.
- Compute $\vec{r}_\phi \times \vec{r}_\theta$ and check its direction matches "upward/outward".
- Evaluate $\iint_D \vec{F}(\vec{r})\cdot(\vec{r}_\phi\times\vec{r}_\theta)\,dA$.

**EXECUTE**:
1. $\vec{r}_\phi = \langle \cos\phi\cos\theta, \cos\phi\sin\theta, -\sin\phi\rangle$, $\vec{r}_\theta = \langle -\sin\phi\sin\theta, \sin\phi\cos\theta, 0\rangle$.
2. $\vec{r}_\phi\times\vec{r}_\theta = \langle \sin^2\phi\cos\theta, \sin^2\phi\sin\theta, \sin\phi\cos\phi\rangle = \sin\phi\,\vec{r}(\phi,\theta)$ (outward since $\sin\phi\geq 0$).
3. $\vec{F}(\vec{r}) = \vec{r}$, so $\vec{F}\cdot(\vec{r}_\phi\times\vec{r}_\theta) = \sin\phi\,|\vec{r}|^2 = \sin\phi$.
4. Flux $= \int_0^{2\pi}\int_0^{\pi/2}\sin\phi\,d\phi\,d\theta = 2\pi \cdot 1 = 2\pi$.

**EVALUATE**: On the unit sphere $\vec{F} = \vec{r}$ equals the outward unit normal, so $\vec{F}\cdot\hat{n} = 1$ and flux equals surface area of hemisphere $= 2\pi(1)^2 = 2\pi$. Matches.

## 15.8 Curl of a Vector Field

Q: Why is curl called a measure of rotation?
A: At a point, $\nabla\times\vec{F}$ points along the axis about which the field tends to rotate a tiny paddle wheel, and its magnitude gives twice the angular speed of that rotation. A zero curl means the field has no local swirling tendency at that point.

C: The [curl] of $\vec{F} = \langle P, Q, R\rangle$ is $\nabla\times\vec{F} = \langle R_y - Q_z,\ P_z - R_x,\ Q_x - P_y\rangle$, where subscripts denote partial derivatives.

C: A vector field with $\nabla\times\vec{F} = \vec{0}$ everywhere on a simply connected domain is called [irrotational], and is necessarily conservative.

Q: Why must conservative fields have zero curl?
A: A conservative field satisfies $\vec{F} = \nabla f$ for some scalar $f$, and $\nabla\times(\nabla f) = \vec{0}$ by equality of mixed partials (Clairaut's theorem). So computing curl gives a fast test: nonzero curl rules out conservativity.

## 15.9 Divergence of a Vector Field

Q: Why is divergence interpreted as net outflow per unit volume?
A: $\nabla\cdot\vec{F}$ at a point measures how much the field spreads away from that point relative to how much it flows in, per infinitesimal volume. Positive divergence marks a source; negative divergence marks a sink; zero means flow in equals flow out locally.

C: The [divergence] of $\vec{F} = \langle P, Q, R\rangle$ is $\nabla\cdot\vec{F} = P_x + Q_y + R_z$, the sum of partial derivatives of each component with respect to its own variable.

C: A vector field satisfying $\nabla\cdot\vec{F} = 0$ everywhere is called [incompressible] (or solenoidal), with no sources or sinks.

Q: Why is $\nabla \cdot (\nabla \times \vec{F}) = 0$ identically?
A: By equality of mixed second partial derivatives, the terms in the expansion cancel in pairs. Geometrically, a curl field has no sources or sinks, since rotation neither creates nor destroys the quantity being circulated.

## 15.10 Stokes' Theorem

Q: Why should circulation around the boundary of $S$ equal the integrated curl over $S$?
A: Curl measures infinitesimal circulation density, so summing it over the surface accumulates all the tiny swirls. Interior circulations between adjacent patches cancel pairwise, leaving only the circulation along the outer boundary — giving the global line integral.

C: [Stokes' Theorem] states $\oint_{\partial S} \vec{F}\cdot d\vec{r} = \iint_S (\nabla\times\vec{F})\cdot d\vec{S}$ for an oriented surface $S$ with consistently oriented boundary $\partial S$.

Q: What is the orientation rule between $S$ and $\partial S$ in Stokes' Theorem?
A: Use the right-hand rule: if the thumb points along $\hat{n}$ (the chosen surface normal), the fingers curl in the positive direction of $\partial S$. Equivalently, walking along $\partial S$ with head toward $\hat{n}$, the surface is on your left.

C: Stokes' Theorem requires $S$ to be a [piecewise-smooth oriented surface] bounded by a simple, closed, piecewise-smooth curve $\partial S$.

Q: When is it easier to evaluate $\iint_S (\nabla\times\vec{F})\cdot d\vec{S}$ than $\oint_{\partial S}\vec{F}\cdot d\vec{r}$?
A: When the boundary curve is awkward (e.g., a complicated intersection) but the curl is simple, or when swapping to a different surface with the same boundary makes the surface integral trivial. Stokes lets you replace $S$ by any surface sharing $\partial S$.

## 15.11 Stokes' as a Generalization of Green's Theorem

Q: Why is Green's Theorem the planar case of Stokes' Theorem?
A: Let $S$ be a planar region in the $xy$-plane with upward normal $\hat{k}$. Then $(\nabla\times\vec{F})\cdot\hat{k} = Q_x - P_y$, and Stokes reduces to $\oint_C P\,dx + Q\,dy = \iint_D (Q_x - P_y)\,dA$, which is exactly Green's Theorem.

C: If $S$ is a region in the $xy$-plane with upward normal, then the scalar form of curl that appears in Stokes' Theorem is $(\nabla\times\vec{F})\cdot\hat{k} = [Q_x - P_y]$, where $P, Q$ are the $x, y$ components of $\vec{F}$.

## 15.12 Divergence (Gauss') Theorem

Q: Why should total outward flux through a closed surface equal the integrated divergence over the enclosed solid?
A: Divergence is local outflow per unit volume, so summing over the solid tallies all the outflow produced inside. Flows between adjacent interior cells cancel, leaving only flow that exits through the outer boundary — which is precisely the flux integral.

C: The [Divergence Theorem] states $\iiint_E \nabla\cdot\vec{F}\,dV = \oiint_{\partial E} \vec{F}\cdot d\vec{S}$, where $E$ is a solid region and $\partial E$ its boundary surface with outward orientation.

C: The Divergence Theorem requires $\partial E$ to be a [closed] piecewise-smooth surface oriented outward, enclosing the solid $E$.

Q: Why does the Divergence Theorem fail for a non-closed surface?
A: Divergence measures net outflow from a volume, but a non-closed surface leaves openings through which flow is unaccounted. Without a closed boundary, there is no enclosed region $E$ for the triple integral to range over.

Q: When is the Divergence Theorem particularly useful?
A: When $\nabla\cdot\vec{F}$ is simple (often constant or zero) even though $\vec{F}$ is complicated on the surface. Converting a hard flux integral to an easy volume integral can save enormous work — especially for closed surfaces with many pieces.

P: Use the Divergence Theorem to compute the outward flux of $\vec{F} = \langle x^3, y^3, z^3\rangle$ through the unit sphere $S: x^2+y^2+z^2 = 1$.

S:
**IDENTIFY**: Flux through a closed surface with outward orientation; ideal Divergence Theorem setup.

**PLAN**:
- Compute $\nabla\cdot\vec{F}$.
- Replace $\oiint_S \vec{F}\cdot d\vec{S}$ with $\iiint_E \nabla\cdot\vec{F}\,dV$ over the unit ball $E$.
- Evaluate using spherical coordinates: $dV = \rho^2\sin\phi\,d\rho\,d\phi\,d\theta$.

**EXECUTE**:
1. $\nabla\cdot\vec{F} = 3x^2 + 3y^2 + 3z^2 = 3\rho^2$ in spherical coordinates.
2. Flux $= \iiint_E 3\rho^2\,dV = \int_0^{2\pi}\!\int_0^\pi\!\int_0^1 3\rho^2 \cdot \rho^2\sin\phi\,d\rho\,d\phi\,d\theta$.
3. Inner: $\int_0^1 3\rho^4\,d\rho = 3/5$. Middle: $\int_0^\pi \sin\phi\,d\phi = 2$. Outer: $\int_0^{2\pi} d\theta = 2\pi$.
4. Flux $= (3/5)(2)(2\pi) = 12\pi/5$.

**EVALUATE**: The divergence $3\rho^2$ is positive everywhere, so net outward flux should be positive — and $12\pi/5 > 0$. Computing the surface integral directly would require $\vec{F}$ dotted with the outward normal $\hat{r}$ giving $x^4+y^4+z^4$ integrated over the sphere — far messier than the volume integral.

## 15.13 The Unifying Pattern

Q: What common structure do FTC, FTLI, Green's, Stokes', and Divergence Theorems share?
A: Each equates the integral of a derivative over a region with the integral of the original function over the region's boundary. The "derivative" varies (ordinary, gradient, 2D curl, 3D curl, divergence), but the pattern "integral of derivative inside = integral of function on boundary" is identical.

C: The [Fundamental Theorem of Calculus] $\int_a^b f'(x)\,dx = f(b) - f(a)$ fits the unification pattern: boundary of $[a,b]$ is the two endpoints, and $f$ is evaluated there.

C: The [Fundamental Theorem of Line Integrals] $\int_C \nabla f \cdot d\vec{r} = f(\vec{r}(b)) - f(\vec{r}(a))$ relates the gradient integrated over a curve to $f$ evaluated at the curve's endpoints (its boundary).

C: [Green's Theorem] relates the 2D-curl $Q_x - P_y$ integrated over a planar region to the line integral of $\vec{F}$ around the region's boundary.

C: [Stokes' Theorem] relates the 3D curl $\nabla\times\vec{F}$ integrated over a surface to the line integral of $\vec{F}$ around the surface's boundary curve.

C: The [Divergence Theorem] relates the divergence $\nabla\cdot\vec{F}$ integrated over a solid to the flux of $\vec{F}$ across the solid's boundary surface.

Q: Why is this unifying pattern called a "generalized Stokes' theorem" in differential geometry?
A: All five theorems are special cases of $\int_M d\omega = \int_{\partial M} \omega$, where $\omega$ is a differential form, $d$ is the exterior derivative, and $M$ is an oriented manifold with boundary $\partial M$. The exterior derivative specializes to $f'$, $\nabla$, curl, or divergence depending on the form's degree.

Q: Across these theorems, what is always traded for what?
A: An integral over an $n$-dimensional region of a derivative of $\vec{F}$ is traded for an integral over the $(n-1)$-dimensional boundary of $\vec{F}$ itself. One step of "integration" cancels one step of "differentiation" and drops dimension by one.
