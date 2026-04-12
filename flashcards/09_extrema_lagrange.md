+++
order = 9
tags = ["math", "multivariable-calculus", "extrema", "critical-points", "second-derivative-test", "lagrange-multipliers"]
+++

# Multivariable Calculus — Extrema and Lagrange Multipliers

## 9.1 Local vs Absolute Extrema in Several Variables

Q: What does it mean for $f(x, y)$ to have a local maximum at $(a, b)$?
A: There exists a neighborhood (open disk) around $(a, b)$ such that $f(a, b) \ge f(x, y)$ for every $(x, y)$ in that neighborhood. The value only needs to beat nearby points, not the entire domain. "Local" therefore describes behavior restricted to a small region, not global dominance.

Q: How does an absolute extremum differ from a local extremum in several variables?
A: An absolute (global) extremum compares $f(a, b)$ to all points in the domain, not just a neighborhood. Every absolute extremum in the interior is automatically a local extremum, but local extrema are not necessarily absolute. Absolute extrema may also occur on the boundary of the domain.

C: A point $(a, b)$ is a [local minimum] of $f$ if $f(a, b) \le f(x, y)$ for all $(x, y)$ in some neighborhood of $(a, b)$.

Q: Why is the distinction between local and absolute extrema more delicate in 2D than in 1D?
A: In one variable, "nearby" means an open interval; in two variables, it means an open disk in every direction. A function can dip below a candidate point along some direction that a crude check missed. Rigorous testing therefore requires information about all directions through the point.

## 9.2 Critical Points of $f(x, y)$

C: A [critical point] of $f(x, y)$ is a point in the domain where $\nabla f = \vec{0}$ or where $\nabla f$ is undefined.

Q: What does $\nabla f(a, b) = \vec{0}$ mean concretely?
A: Both partial derivatives vanish simultaneously: $f_x(a, b) = 0$ and $f_y(a, b) = 0$, where $f_x$ and $f_y$ are the partial derivatives with respect to $x$ and $y$. Geometrically, the tangent plane to the surface $z = f(x, y)$ is horizontal at $(a, b, f(a, b))$.

Q: Why include points where $\nabla f$ is undefined as critical points?
A: Local extrema can occur at "kinks" or cusps where the surface has no well-defined tangent plane, for example at the tip of the cone $f(x, y) = \sqrt{x^2 + y^2}$. Those points are still candidate extrema even though no derivative-based test applies. Restricting to $\nabla f = \vec{0}$ alone would miss them.

Q: How do you find the critical points of $f(x, y) = x^2 + xy + y^2 - 3x$?
A: Compute partials: $f_x = 2x + y - 3$ and $f_y = x + 2y$. Set both to zero and solve the linear system: $2x + y = 3$, $x + 2y = 0$. Solving gives $y = -x/2$, then $2x - x/2 = 3$, so $x = 2$, $y = -1$. Unique critical point $(2, -1)$.

## 9.3 Why Local Extrema Occur Only at Critical Points

Q: Before reading the justification, predict: if $(a, b)$ is an interior local extremum of $f$, why must $\nabla f(a, b) = \vec{0}$?
A: If a partial derivative were nonzero, you could move a tiny step in that coordinate direction to increase or decrease $f$, contradicting the extremum. So both partials must vanish. This is the multivariable generalization of Fermat's one-variable theorem.

Q: How does the proof that interior extrema are critical points use single-variable Fermat's theorem?
A: Fix $y = b$ and view $g(x) = f(x, b)$ as a one-variable function. If $f$ has a local extremum at $(a, b)$, then $g$ has a local extremum at $x = a$, so by Fermat, $g'(a) = f_x(a, b) = 0$. Repeating with $x = a$ fixed gives $f_y(a, b) = 0$, so $\nabla f(a, b) = \vec{0}$.

Q: Does $\nabla f(a, b) = \vec{0}$ guarantee that $(a, b)$ is a local extremum?
A: No. The condition is necessary but not sufficient: every interior extremum is a critical point, but not every critical point is an extremum. Saddle points are the classic counterexample, so critical points must be classified further using the second derivative test or direct analysis.

## 9.4 Saddle Points

C: A [saddle point] is a critical point of $f$ that is neither a local maximum nor a local minimum.

Q: What does a saddle point look like geometrically for $f(x, y) = x^2 - y^2$ at the origin?
A: Along the $x$-axis ($y = 0$), $f = x^2$ has a minimum at $0$; along the $y$-axis ($x = 0$), $f = -y^2$ has a maximum at $0$. The surface rises in one direction and falls in the perpendicular direction, resembling a horse saddle. Every neighborhood contains points above and below $f(0, 0) = 0$.

Q: Why can a critical point fail to be an extremum?
A: The gradient being zero means the tangent plane is horizontal, but the surface may curve upward in some directions and downward in others. The first derivatives alone carry no curvature information. Second-order behavior (the Hessian) is needed to distinguish true extrema from saddles.

## 9.5 The Hessian Matrix

C: For a twice-continuously-differentiable function $f(x, y)$, the [Hessian matrix] is $H = \begin{pmatrix} f_{xx} & f_{xy}\\ f_{xy} & f_{yy}\end{pmatrix}$, where $f_{xx}$, $f_{yy}$ are the pure second partials and $f_{xy}$ is the mixed partial.

Q: Why is the Hessian symmetric (i.e., $f_{xy} = f_{yx}$)?
A: Clairaut's theorem guarantees that for functions with continuous second partial derivatives, the order of partial differentiation does not matter: $f_{xy} = f_{yx}$. Hence the off-diagonal entries of $H$ are equal, making $H$ a symmetric matrix.

Q: What information does the Hessian encode about a critical point?
A: It records second-order curvature: how quickly $f$ bends in each coordinate direction and how $x$-curvature couples with $y$-curvature via $f_{xy}$. Together these entries determine whether $f$ behaves like a bowl, an upside-down bowl, or a saddle near the critical point.

C: The Hessian is the multivariable analog of the [second derivative] in single-variable calculus.

## 9.6 The Discriminant $D$

C: The [discriminant] of $f(x, y)$ at a point is $D = f_{xx}\,f_{yy} - (f_{xy})^2$, where $f_{xx}$, $f_{yy}$, $f_{xy}$ are evaluated at that point.

Q: How is the discriminant $D$ related to the Hessian?
A: $D$ is precisely the determinant of the Hessian: $\det H = f_{xx}f_{yy} - (f_{xy})^2$. So $D$ measures whether the Hessian is invertible and encodes the product of its eigenvalues $\lambda_1 \lambda_2 = \det H$.

Q: Why does the sign of $D$ determine whether the Hessian's eigenvalues have the same or opposite signs?
A: For a symmetric $2 \times 2$ matrix, $\det H = \lambda_1 \lambda_2$. If $D > 0$, eigenvalues share a sign (both positive or both negative); if $D < 0$, they have opposite signs; if $D = 0$, at least one eigenvalue is zero. The sign pattern of eigenvalues is exactly what classifies the critical point.

## 9.7 Second Derivative Test

C: If $\nabla f(a, b) = \vec{0}$ and $D(a, b) > 0$ with $f_{xx}(a, b) > 0$, then $(a, b)$ is a [local minimum] of $f$.

C: If $\nabla f(a, b) = \vec{0}$ and $D(a, b) > 0$ with $f_{xx}(a, b) < 0$, then $(a, b)$ is a [local maximum] of $f$.

C: If $\nabla f(a, b) = \vec{0}$ and $D(a, b) < 0$, then $(a, b)$ is a [saddle point] of $f$.

Q: What does $D = 0$ tell you in the second derivative test?
A: The test is inconclusive: the critical point could be a local minimum, local maximum, or saddle, and the second-order information alone cannot decide. Classification must proceed by other means, such as examining the function along specific curves through the point or using higher-order Taylor terms.

Q: Why isn't $f_{yy}$ used as the sign indicator when $D > 0$?
A: When $D = f_{xx}f_{yy} - (f_{xy})^2 > 0$, we have $f_{xx}f_{yy} > (f_{xy})^2 \ge 0$, so $f_{xx}$ and $f_{yy}$ must have the same sign. Either one indicates whether the bowl opens up or down; $f_{xx}$ is the convention.

## 9.8 Why the Second Derivative Test Works

Q: Intuitively, why does $D > 0$ with $f_{xx} > 0$ force a local minimum rather than a saddle?
A: $D > 0$ means both Hessian eigenvalues have the same sign, so the surface curves the same way in every direction — either all upward or all downward. The sign of $f_{xx}$ (or equivalently the eigenvalue sign) then says which way: positive means upward-curving in every direction, i.e., a bowl with a minimum at the center.

Q: How does diagonalizing the Hessian justify the second derivative test?
A: The symmetric Hessian $H$ can be diagonalized by rotating coordinates to its eigenvector axes, giving a principal-axis quadratic form $\lambda_1 u^2 + \lambda_2 v^2$ locally. The signs of $\lambda_1, \lambda_2$ determine the local shape: both positive gives a minimum, both negative a maximum, opposite signs a saddle. These sign patterns are detected by $D$ and $f_{xx}$.

Q: What does $D < 0$ say about the Hessian's eigenvalues and the local geometry?
A: $D < 0$ means $\lambda_1 \lambda_2 < 0$, so one eigenvalue is positive and the other negative. Along one principal axis the surface curves up, along the perpendicular axis it curves down — the defining geometric feature of a saddle.

## 9.9 Extreme Value Theorem on Closed and Bounded Regions

C: A set in $\mathbb{R}^2$ is [closed] if it contains all its boundary points, and [bounded] if it fits inside some disk of finite radius.

Q: What does the multivariable Extreme Value Theorem guarantee?
A: If $f$ is continuous on a closed and bounded region $R \subset \mathbb{R}^2$, then $f$ attains both an absolute maximum and an absolute minimum on $R$. Existence is guaranteed; you only need to find where they occur.

Q: Why does the Extreme Value Theorem require both closedness and boundedness?
A: Boundedness prevents $f$ from escaping to $\pm\infty$ along unbounded directions, and closedness prevents extrema from "leaking out" through missing boundary points. Drop either hypothesis and a continuous function can fail to attain its supremum, e.g., $f(x, y) = x$ on the open unit disk.

## 9.10 Absolute Extrema Procedure

P: How do you find the absolute extrema of a continuous $f(x, y)$ on a closed, bounded region $R$?

S:
**IDENTIFY**: Two-stage absolute extremum problem on a closed bounded region; EVT guarantees the extrema exist.

**PLAN**: The absolute extrema occur either at interior critical points or on the boundary of $R$; examine each region separately.

**EXECUTE**:
1. Find all interior critical points: solve $\nabla f = \vec{0}$ inside $R$ and record $f$-values.
2. Parametrize or otherwise reduce $f$ on the boundary $\partial R$ to a lower-dimensional optimization problem; find its critical points.
3. Include boundary corners or non-smooth points where pieces of $\partial R$ meet.
4. Evaluate $f$ at every candidate collected above.

**EVALUATE**: The largest value is the absolute maximum and the smallest is the absolute minimum; no second derivative test is needed since we are comparing numerical values directly.

Q: Why do you NOT need the second derivative test when computing absolute extrema on a closed, bounded region?
A: You produce a finite list of candidate points (interior critical points plus boundary candidates). Since EVT guarantees the absolute extrema exist among these candidates, simply comparing $f$-values identifies them. Classifying critical points as local max/min/saddle is irrelevant for a direct value comparison.

## 9.11 Parametrizing the Boundary

Q: Why does parametrizing the boundary reduce the problem to one variable?
A: The boundary of a planar region is (piecewise) a curve of dimension one. A parametrization $\vec{r}(t) = (x(t), y(t))$ converts $f$ restricted to the boundary into $g(t) = f(x(t), y(t))$, a function of a single parameter. Single-variable calculus then locates its critical points by solving $g'(t) = 0$.

Q: How do you search for boundary extrema on the unit circle $x^2 + y^2 = 1$?
A: Parametrize as $x = \cos t$, $y = \sin t$ for $t \in [0, 2\pi]$. Define $g(t) = f(\cos t, \sin t)$, compute $g'(t)$ via the chain rule, and solve $g'(t) = 0$ to find candidate values of $t$. Evaluate $f$ at the corresponding $(x, y)$ points.

C: When the boundary is piecewise smooth, you must also check the [corner points] where smooth pieces meet, since the parametrization is not differentiable there.

## 9.12 Motivating Lagrange Multipliers

Q: What kind of problem do Lagrange multipliers solve?
A: Constrained optimization: find the extrema of $f(x, y)$ subject to $g(x, y) = c$, where the constraint confines $(x, y)$ to a curve (or surface in higher dimensions). We want extrema of $f$ restricted to this constraint set, not extrema of $f$ over the whole plane.

Q: Why can't we just solve $\nabla f = \vec{0}$ for constrained problems?
A: Unconstrained critical points of $f$ are usually not on the constraint curve, and constrained extrema typically occur where $\nabla f \ne \vec{0}$. The relevant notion of "critical" changes: we need points where $f$ has no tangential change along the constraint, not zero gradient overall.

## 9.13 Geometric Idea Behind Lagrange

Q: Before the formal derivation, predict: what must be true about the level curves of $f$ and $g$ at a constrained extremum?
A: They should be tangent — touching without crossing. If they crossed, you could slide along $g = c$ to move to a higher or lower level curve of $f$, contradicting extremality.

Q: Why must $\nabla f$ and $\nabla g$ be parallel at a constrained extremum?
A: At a constrained extremum the level curves $f = k$ and $g = c$ are tangent, so they share a common tangent line. Gradients are perpendicular to level curves, so $\nabla f$ and $\nabla g$ are both normal to the same tangent line and therefore parallel (or one is zero).

Q: What goes wrong if $\nabla f$ has a component along the constraint curve?
A: That tangential component predicts a direction along the constraint in which $f$ increases, and the opposite direction in which $f$ decreases. Therefore $(x, y)$ cannot be a constrained extremum. At an extremum, $\nabla f$ must be purely normal to the constraint — parallel to $\nabla g$.

## 9.14 The Lagrange Multiplier Equation

C: At a constrained extremum of $f$ subject to $g = c$, there exists a scalar [$\lambda$] (the Lagrange multiplier) such that $\nabla f = \lambda \nabla g$.

Q: What does the number $\lambda$ represent in $\nabla f = \lambda \nabla g$?
A: It is the proportionality factor between the two parallel gradients at the extremum; its sign and magnitude record how $\nabla f$ scales relative to $\nabla g$. It has no geometric meaning on its own but gains physical interpretation as a sensitivity (see 9.17).

Q: What happens if $\nabla g = \vec{0}$ at a candidate point?
A: The Lagrange condition $\nabla f = \lambda \nabla g$ becomes $\nabla f = \vec{0}$ for any $\lambda$, and the geometric "tangent constraint curve" argument breaks down because the constraint curve is singular there. Such points must be checked separately as additional candidates.

## 9.15 Standard Lagrange Procedure

P: How do you use Lagrange multipliers to find the extrema of $f(x, y)$ subject to $g(x, y) = c$?

S:
**IDENTIFY**: Constrained optimization problem with a single equality constraint.

**PLAN**: Set up the Lagrange system $\nabla f = \lambda \nabla g$ together with $g = c$, solve for all candidate points, then compare $f$-values.

**EXECUTE**:
1. Write the component equations: $f_x = \lambda g_x$ and $f_y = \lambda g_y$.
2. Append the constraint $g(x, y) = c$, giving three equations in $(x, y, \lambda)$.
3. Solve the system — often by eliminating $\lambda$ from the first two equations, then substituting into the constraint.
4. Also check points where $\nabla g = \vec{0}$ as separate candidates.

**EVALUATE**: Evaluate $f$ at each candidate; largest value is the constrained maximum, smallest is the constrained minimum. If the constraint set is closed and bounded, EVT guarantees both exist.

Q: Why is eliminating $\lambda$ usually a good first step?
A: $\lambda$ is an auxiliary unknown with no geometric interest — only the $(x, y)$ candidates matter. Dividing or cross-multiplying the two component equations cancels $\lambda$, leaving a relation purely between $x$ and $y$ that combines with the constraint to a two-equation system.

## 9.16 Two Constraints

C: For two constraints $g(x, y, z) = c_1$ and $h(x, y, z) = c_2$, the Lagrange condition becomes $\nabla f = \lambda\nabla g + \mu\nabla h$, where $\lambda$ and $\mu$ are [Lagrange multipliers] for the two constraints.

Q: Why does a second constraint introduce a second multiplier $\mu$?
A: Two independent constraints restrict motion to the intersection curve of $g = c_1$ and $h = c_2$. At an extremum along this curve, $\nabla f$ must lie in the plane spanned by $\nabla g$ and $\nabla h$ (both of which are normal to the curve). The coefficients $\lambda$ and $\mu$ are the components of $\nabla f$ in that basis.

Q: How many equations and unknowns appear in a two-constraint Lagrange system in $\mathbb{R}^3$?
A: Unknowns are $x, y, z, \lambda, \mu$ — five total. Equations are three from $\nabla f = \lambda\nabla g + \mu\nabla h$ plus the two constraints, again five total. The system is square and typically yields discrete solutions.

## 9.17 Interpretation of $\lambda$

Q: What does $\lambda$ represent physically or economically when we maximize $f$ subject to $g = c$?
A: $\lambda$ is the rate of change of the optimal value of $f$ as the constraint level $c$ varies: if $f^*(c)$ denotes the max subject to $g = c$, then $df^*/dc = \lambda$. It measures the marginal payoff from relaxing the constraint slightly.

Q: In economics, why is $\lambda$ often called the "shadow price" of the constraint?
A: If $f$ is utility or profit and $g = c$ is a budget or resource constraint, $\lambda$ equals the extra utility/profit gained per unit increase of the resource. It tells you what a marginal unit of the constrained resource is worth at the optimum — its "implicit" or "shadow" price.

C: The derivative of the optimal value $f^*(c)$ with respect to the constraint level $c$ equals the [Lagrange multiplier $\lambda$] (envelope theorem).

## 9.18 Worked Example: Classifying Critical Points

P: Classify all critical points of $f(x, y) = x^3 + y^3 - 3xy$.

S:
**IDENTIFY**: Unconstrained classification; apply the second derivative test.

**PLAN**: Compute $\nabla f$, solve $\nabla f = \vec{0}$ for critical points, compute Hessian entries, evaluate $D$ and $f_{xx}$ at each point.

**EXECUTE**:
1. Partials: $f_x = 3x^2 - 3y$ and $f_y = 3y^2 - 3x$. Set to zero: $y = x^2$ and $x = y^2$.
2. Substitute: $x = (x^2)^2 = x^4$, so $x^4 - x = 0$, giving $x(x^3 - 1) = 0$, hence $x = 0$ or $x = 1$. Corresponding $y$ values: $y = 0$ and $y = 1$. Critical points: $(0, 0)$ and $(1, 1)$.
3. Second partials: $f_{xx} = 6x$, $f_{yy} = 6y$, $f_{xy} = -3$. Discriminant $D = 36xy - 9$.
4. At $(0, 0)$: $D = -9 < 0$, so $(0, 0)$ is a saddle point.
5. At $(1, 1)$: $D = 36 - 9 = 27 > 0$ and $f_{xx}(1, 1) = 6 > 0$, so $(1, 1)$ is a local minimum with $f(1, 1) = 1 + 1 - 3 = -1$.

**EVALUATE**: Two critical points found and classified by the $D$-test; signs are consistent (saddle near origin, local min at $(1,1)$). Since the domain is all of $\mathbb{R}^2$, which is unbounded, no absolute extremum exists.

## 9.19 Worked Example: Lagrange Multipliers

P: Find the extrema of $f(x, y) = x + y$ subject to the constraint $g(x, y) = x^2 + y^2 = 1$.

S:
**IDENTIFY**: Constrained optimization on the unit circle; constraint set is closed and bounded so EVT guarantees both extrema exist.

**PLAN**: Apply $\nabla f = \lambda\nabla g$ together with $g = 1$, solve for $(x, y, \lambda)$, then compare $f$-values.

**EXECUTE**:
1. Gradients: $\nabla f = (1, 1)$ and $\nabla g = (2x, 2y)$.
2. Lagrange equations: $1 = 2\lambda x$ and $1 = 2\lambda y$, so $2\lambda x = 2\lambda y$, giving $x = y$ (note $\lambda \ne 0$, else $1 = 0$).
3. Substitute into constraint: $x^2 + x^2 = 1$, so $x^2 = 1/2$, giving $x = y = \pm\frac{1}{\sqrt{2}}$.
4. Candidate points: $\left(\tfrac{1}{\sqrt 2}, \tfrac{1}{\sqrt 2}\right)$ and $\left(-\tfrac{1}{\sqrt 2}, -\tfrac{1}{\sqrt 2}\right)$.
5. Values: $f\left(\tfrac{1}{\sqrt 2}, \tfrac{1}{\sqrt 2}\right) = \sqrt{2}$ (maximum); $f\left(-\tfrac{1}{\sqrt 2}, -\tfrac{1}{\sqrt 2}\right) = -\sqrt{2}$ (minimum).

**EVALUATE**: Geometrically, the level lines $x + y = k$ are lines of slope $-1$; the extreme values of $k$ reachable while touching the unit circle occur where such a line is tangent to the circle along the diagonal $y = x$ — exactly the points we found. Values $\pm\sqrt{2}$ match the expected radius-scaled bound from the Cauchy-Schwarz inequality.
