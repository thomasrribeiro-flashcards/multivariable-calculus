+++
order = 14
tags = ["math", "multivariable-calculus", "greens-theorem", "conservative-fields", "path-independence", "potential-functions"]
+++

# Multivariable Calculus — Green's Theorem and Conservative Fields

## 14.1 Conservative Vector Fields

Q: Why do we single out vector fields of the form $\vec{F} = \nabla f$ for special study?
A: Because line integrals of such fields depend only on the endpoints of the curve, not the path taken. This makes work computations trivial once the scalar function $f$ is known, and it mirrors how physical forces like gravity and electrostatics behave, where energy depends only on position.

C: A vector field $\vec{F}$ is called [conservative] if there exists a scalar function $f$ such that $\vec{F} = \nabla f$.

C: When $\vec{F} = \nabla f$, the scalar function $f$ is called a [potential function] for $\vec{F}$.

Q: What does $\nabla f$ denote for a scalar function $f(x,y)$?
A: The gradient vector $\nabla f = \langle \partial f/\partial x, \partial f/\partial y\rangle$, whose components are the partial derivatives of $f$ with respect to each coordinate.

C: If $\vec{F} = \langle P, Q\rangle$ is conservative with potential $f$, then $P = [\partial f/\partial x]$ and $Q = \partial f/\partial y$.

Q: Why is the sign convention in physics often $\vec{F} = -\nabla U$ rather than $\vec{F} = \nabla f$?
A: Physicists define potential energy $U$ so that force points in the direction of decreasing potential energy, matching the intuition that objects accelerate toward lower energy states. Mathematically either sign works; the chosen convention just flips the sign of the potential.

## 14.2 Fundamental Theorem for Line Integrals

Q: Before stating the Fundamental Theorem for Line Integrals, predict: if $\vec{F} = \nabla f$, what should $\int_C \vec{F}\cdot d\vec{r}$ depend on?
A: Only the endpoints of $C$, because the gradient measures the rate of change of $f$, so integrating it along a path should accumulate the net change in $f$ between start and end.

C: The [Fundamental Theorem for Line Integrals] states that if $\vec{F} = \nabla f$ and $C$ runs from $A$ to $B$, then $\int_C \vec{F}\cdot d\vec{r} = f(B) - f(A)$.

Q: Why does the Fundamental Theorem for Line Integrals generalize the single-variable FTC?
A: The single-variable FTC says $\int_a^b f'(x)\,dx = f(b) - f(a)$, accumulating a derivative gives a net change. FTLI replaces $f'$ with $\nabla f$ and the interval $[a,b]$ with a curve $C$, but the idea is identical: integrating the rate of change along the path yields the net change in $f$.

C: For a conservative field with potential $f$, the work done along any curve from $A$ to $B$ equals $[f(B) - f(A)]$, independent of the path.

## 14.3 Path Independence

Q: Why is path independence a useful property for a vector field?
A: It means we can evaluate line integrals without parametrizing the curve; we just need the endpoints and a potential function. It also reflects the physical idea of a conservative force, where work done depends only on displacement, not the route.

C: A line integral $\int_C \vec{F}\cdot d\vec{r}$ is [path independent] on a region $D$ if its value depends only on the endpoints of $C$, not on the specific curve chosen within $D$.

Q: What is the relationship between conservative fields and path independence on a connected domain?
A: They are equivalent: a continuous vector field on an open connected region is conservative if and only if its line integrals are path independent. So finding a potential and checking path independence are two sides of the same coin.

## 14.4 Closed Curves and Conservative Fields

Q: Why should $\oint_C \vec{F}\cdot d\vec{r} = 0$ for every closed curve if $\vec{F}$ is conservative?
A: A closed curve has the same starting and ending point $A = B$, so by FTLI the integral equals $f(A) - f(A) = 0$. Physically, moving around a loop in a conservative force field does zero net work.

C: A continuous field $\vec{F}$ on an open connected region is conservative if and only if $\oint_C \vec{F}\cdot d\vec{r} = [0]$ for every closed curve $C$ in the region.

C: A region $D$ is called [simply connected] if it is connected and every closed curve in $D$ can be continuously shrunk to a point without leaving $D$.

Q: Why does the equivalence "closed-loop integral zero iff conservative" require simply connected domains?
A: On a region with a hole, a field may satisfy the local conservative test $\partial P/\partial y = \partial Q/\partial x$ everywhere but still give nonzero integrals around loops that encircle the hole. Simple connectedness rules out such loops by ensuring every closed curve bounds a region entirely inside $D$.

## 14.5 Test for Conservative Fields in 2D

Q: Why should we expect $\partial P/\partial y = \partial Q/\partial x$ when $\vec{F} = \langle P, Q\rangle$ is conservative?
A: If $\vec{F} = \nabla f$, then $P = f_x$ and $Q = f_y$, so $\partial P/\partial y = f_{xy}$ and $\partial Q/\partial x = f_{yx}$. By Clairaut's theorem on equality of mixed partials (for $f \in C^2$), these are equal, giving the test.

C: For $\vec{F} = \langle P(x,y), Q(x,y)\rangle$ with continuous partials on a simply connected region, $\vec{F}$ is conservative if and only if $[\partial P/\partial y = \partial Q/\partial x]$.

Q: Why is $\partial P/\partial y = \partial Q/\partial x$ only a necessary condition on non–simply connected regions?
A: The equality follows locally from equality of mixed partials, but globally a potential may fail to exist if the domain has holes. The classic example is $\vec{F} = \langle -y/(x^2+y^2), x/(x^2+y^2)\rangle$ on the punctured plane, which passes the test but has $\oint \vec{F}\cdot d\vec{r} = 2\pi$ around the origin.

Q: Given $\vec{F} = \langle 2xy, x^2 + 3y^2\rangle$, is $\vec{F}$ conservative?
A: Yes. With $P = 2xy$ and $Q = x^2 + 3y^2$ we get $\partial P/\partial y = 2x$ and $\partial Q/\partial x = 2x$. The partials agree on all of $\mathbb{R}^2$ (simply connected), so $\vec{F}$ is conservative.

## 14.6 Finding a Potential Function

Q: Why does the procedure "integrate $P$ with respect to $x$, then adjust using $Q$" recover a potential function?
A: If $\vec{F} = \nabla f$ then $f_x = P$, so integrating $P$ with respect to $x$ recovers $f$ up to a function $g(y)$ of $y$ alone. Differentiating with respect to $y$ and matching $Q$ then pins down $g'(y)$, determining $f$ up to a constant.

C: To find a potential for $\vec{F} = \langle P, Q\rangle$: integrate $P$ with respect to $x$ to get $f(x,y) = \int P\,dx + [g(y)]$, then use $f_y = Q$ to solve for $g(y)$.

Q: Why is a potential function only unique up to an additive constant?
A: If $\nabla f = \nabla g$, then $\nabla(f - g) = 0$, so $f - g$ is constant on any connected region. Adding a constant does not change the gradient, so potentials form an equivalence class differing by constants.

P: Verify that $\vec{F} = \langle 2xy, x^2 + 3y^2\rangle$ is conservative, find its potential function, and use FTLI to evaluate $\int_C \vec{F}\cdot d\vec{r}$ where $C$ runs from $(0,0)$ to $(1,2)$.

S:
**IDENTIFY**: Conservative field problem on $\mathbb{R}^2$ (simply connected); asked to test, find potential, and evaluate line integral using FTLI.

**PLAN**:
- Apply the test $\partial P/\partial y \stackrel{?}{=} \partial Q/\partial x$ with $P = 2xy$ and $Q = x^2 + 3y^2$.
- Integrate $P$ with respect to $x$ to get a candidate $f(x,y)$ with unknown $g(y)$.
- Match $f_y = Q$ to determine $g(y)$.
- Apply FTLI: $\int_C \vec{F}\cdot d\vec{r} = f(B) - f(A)$.

**EXECUTE**:
1. $\partial P/\partial y = 2x$ and $\partial Q/\partial x = 2x$. Equal on $\mathbb{R}^2$, so $\vec{F}$ is conservative.
2. $f(x,y) = \int 2xy\,dx = x^2 y + g(y)$.
3. $f_y = x^2 + g'(y)$. Set equal to $Q = x^2 + 3y^2$, so $g'(y) = 3y^2$, giving $g(y) = y^3$ (drop the constant).
4. Potential: $f(x,y) = x^2 y + y^3$.
5. FTLI: $\int_C \vec{F}\cdot d\vec{r} = f(1,2) - f(0,0) = (1^2\cdot 2 + 2^3) - 0 = 2 + 8 = 10$.

**EVALUATE**: Check $\nabla f = \langle 2xy, x^2 + 3y^2\rangle = \vec{F}$. The answer $10$ is independent of the path, as expected for a conservative field.

## 14.7 Green's Theorem (Circulation Form)

Q: Why should a line integral around a closed curve be expressible as a double integral over the enclosed region?
A: The closed-curve integral measures circulation on the boundary, and circulation is generated by local rotation (curl) inside the region. Summing the infinitesimal rotations over the interior should reproduce the net boundary circulation, which is exactly what Green's theorem asserts.

C: [Green's theorem (circulation form)] states $\oint_C P\,dx + Q\,dy = \iint_D\left(\dfrac{\partial Q}{\partial x} - \dfrac{\partial P}{\partial y}\right)dA$, where $C$ is the positively oriented boundary of region $D$, and $P,Q$ have continuous partial derivatives on $D$.

Q: What is the scalar quantity $\partial Q/\partial x - \partial P/\partial y$ called, and what does it measure?
A: It is the scalar (2D) curl of $\vec{F} = \langle P, Q\rangle$, measuring the local counterclockwise rotation of the field at a point. Its sign tells whether a tiny paddle wheel placed in the field would spin counterclockwise (positive) or clockwise (negative).

Q: How does Green's theorem immediately prove that conservative fields have zero circulation?
A: If $\vec{F} = \nabla f$ is conservative, then $\partial Q/\partial x - \partial P/\partial y = f_{yx} - f_{xy} = 0$, so the double integral is zero. Hence $\oint_C \vec{F}\cdot d\vec{r} = 0$ around every closed curve bounding a region in the domain.

## 14.8 Orientation of the Boundary

Q: Why must we specify orientation when applying Green's theorem?
A: Reversing the direction of traversal flips the sign of $\oint_C P\,dx + Q\,dy$, so the theorem only holds for a specific convention. Fixing positive orientation removes the ambiguity and aligns the line integral's sign with the curl integral over the region.

C: The boundary $C$ of $D$ is [positively oriented] when it is traversed counterclockwise, so that the region $D$ lies on the left as you walk along $C$.

Q: How do we orient the boundary of a region with holes for Green's theorem?
A: The outer boundary is traversed counterclockwise and each inner (hole) boundary is traversed clockwise, so that $D$ always lies on the left. This keeps the theorem $\oint_{\partial D} = \iint_D (Q_x - P_y)\,dA$ valid for multiply connected regions.

## 14.9 Green's Theorem (Flux Form)

Q: Why does flux of $\vec{F}$ across a closed curve equal the double integral of the divergence?
A: Divergence measures the local rate at which the field "sources" or "sinks" fluid per unit area. Summing these local source/sink rates over $D$ must match the net outward flow across the boundary, by conservation of flow.

C: [Green's theorem (flux form)] states $\oint_C \vec{F}\cdot\hat{n}\,ds = \iint_D\left(\dfrac{\partial P}{\partial x} + \dfrac{\partial Q}{\partial y}\right)dA$, where $\hat{n}$ is the outward unit normal to $C$ and $\vec{F} = \langle P, Q\rangle$.

C: The scalar $\partial P/\partial x + \partial Q/\partial y$ is called the [divergence] of $\vec{F} = \langle P, Q\rangle$, written $\nabla\cdot\vec{F}$.

Q: How are the circulation and flux forms of Green's theorem related?
A: They are the same identity applied to a rotated field: replacing $\vec{F} = \langle P, Q\rangle$ with $\langle -Q, P\rangle$ swaps the tangential and normal line integrals, turning the curl integrand into a divergence integrand. One form computes circulation; the other computes outward flux.

## 14.10 Area via Green's Theorem

Q: Why can Green's theorem be used to compute area with a boundary integral?
A: Choosing $P,Q$ so that $Q_x - P_y = 1$ makes the double integral in Green's theorem equal to the area of $D$. The theorem then converts this area into a line integral around the boundary, which is often easier to parametrize than the 2D region.

C: The area of $D$ enclosed by a positively oriented curve $C$ satisfies $A = [\tfrac{1}{2}\oint_C (x\,dy - y\,dx)]$.

Q: Why does choosing $P = -y/2$, $Q = x/2$ give the symmetric area formula $A = \tfrac{1}{2}\oint_C x\,dy - y\,dx$?
A: With this choice, $Q_x - P_y = 1/2 - (-1/2) = 1$, so $\iint_D (Q_x - P_y)\,dA = \iint_D 1\,dA = A$. Green's theorem then converts the double integral into the symmetric line integral.

## 14.11 Multiply Connected Regions

Q: Why does Green's theorem extend to regions with holes?
A: A multiply connected region can be cut along internal segments into simply connected pieces. Applying Green's theorem to each piece and adding, the interior cuts cancel (traversed once in each direction), leaving only the outer boundary counterclockwise and each hole boundary clockwise.

C: On a region with holes, Green's theorem holds provided the outer boundary is oriented counterclockwise and each [inner hole boundary] is oriented clockwise.

Q: Why can $\vec{F} = \langle -y/(x^2+y^2), x/(x^2+y^2)\rangle$ pass the test $P_y = Q_x$ yet fail to be conservative on the punctured plane?
A: The test is only sufficient on simply connected regions, and the punctured plane is not simply connected. A direct calculation gives $\oint \vec{F}\cdot d\vec{r} = 2\pi$ around the origin, so no global potential can exist even though mixed partials agree away from the singularity.

## 14.12 Applying Green's Theorem

P: Use Green's theorem to evaluate $\oint_C(y^2\,dx + 3xy\,dy)$, where $C$ is the unit circle $x^2 + y^2 = 1$ traversed counterclockwise.

S:
**IDENTIFY**: Closed-curve line integral of $\vec{F} = \langle P, Q\rangle = \langle y^2, 3xy\rangle$ around a positively oriented simple closed curve bounding a simply connected region $D$ (the unit disk). Green's theorem (circulation form) applies.

**PLAN**:
- Identify $P$ and $Q$, verify $C$ is positively oriented around $D$.
- Compute $\partial Q/\partial x - \partial P/\partial y$ to get the curl integrand.
- Replace the line integral with $\iint_D (Q_x - P_y)\,dA$ and evaluate in polar coordinates $x = r\cos\theta$, $y = r\sin\theta$ with $r\in[0,1]$, $\theta\in[0,2\pi]$.

**EXECUTE**:
1. $P = y^2$, $Q = 3xy$. Then $\partial P/\partial y = 2y$ and $\partial Q/\partial x = 3y$, so $Q_x - P_y = 3y - 2y = y$.
2. By Green's theorem, $\oint_C(y^2\,dx + 3xy\,dy) = \iint_D y\,dA$.
3. In polar coordinates, $y = r\sin\theta$ and $dA = r\,dr\,d\theta$:
$$\iint_D y\,dA = \int_0^{2\pi}\int_0^1 (r\sin\theta)(r\,dr\,d\theta) = \int_0^{2\pi}\sin\theta\,d\theta \cdot \int_0^1 r^2\,dr.$$
4. $\int_0^{2\pi}\sin\theta\,d\theta = 0$ and $\int_0^1 r^2\,dr = 1/3$, so the integral equals $0\cdot\tfrac{1}{3} = 0$.

**EVALUATE**: The answer $0$ is consistent with symmetry: the integrand $y$ is odd in $y$ while the unit disk is symmetric under $y\mapsto -y$, forcing the double integral to vanish. Green's theorem converted an awkward closed-curve integral into a trivial area integral.
