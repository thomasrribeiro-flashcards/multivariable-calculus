+++
order = 8
tags = ["math", "multivariable-calculus", "tangent-plane", "linearization", "differentials", "linear-approximation"]
+++

# Multivariable Calculus — Tangent Planes and Linear Approximation

## 8.1 Why Tangent Planes Generalize Tangent Lines

Q: In single-variable calculus, a tangent line at $x=a$ is the best linear approximation to $f(x)$ near $a$. Before reading, predict: what object should play this role for $z=f(x,y)$ at $(a,b)$?
A: A tangent plane. Since the graph is a 2D surface in 3D space, the "flat" object matching its dimension is a plane, not a line. This plane should touch the surface at $(a,b,f(a,b))$ and locally look like the surface, in the same way a tangent line touches a curve.

Q: Why is a tangent plane the natural generalization of a tangent line for $z=f(x,y)$?
A: A tangent line matches the function's value and slope at a point in 1D. A tangent plane matches the function's value and both partial slopes ($f_x$ and $f_y$) at a point in 2D. In each case we replace a curved graph by the unique flat object that agrees with the function and its first derivatives at that point.

C: The tangent plane at $(a,b)$ is the 2D analogue of the [tangent line] from single-variable calculus.

Q: Geometrically, what does a tangent plane touch and what does it approximate?
A: It touches the surface $z=f(x,y)$ at the single point $(a,b,f(a,b))$ and approximates the surface for $(x,y)$ near $(a,b)$. Far from $(a,b)$ the plane drifts away from the curved surface, just as a tangent line drifts from a curve.

## 8.2 Formula for the Tangent Plane to $z = f(x, y)$

C: The tangent plane to $z=f(x,y)$ at $(a,b)$ has equation $z = f(a,b) + f_x(a,b)(x-a) + [f_y(a,b)(y-b)]$, where $f_x,f_y$ are partial derivatives evaluated at $(a,b)$.

C: The tangent plane equation $z = [f(a,b)] + f_x(a,b)(x-a) + f_y(a,b)(y-b)$ passes through the point $(a,b,f(a,b))$ on the surface.

Q: In the tangent plane formula $z=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$, what role does each term play?
A: $f(a,b)$ is the base height (the $z$-value at the point of tangency). $f_x(a,b)(x-a)$ adds the change predicted by moving in $x$ at the rate $f_x$. $f_y(a,b)(y-b)$ adds the change predicted by moving in $y$ at the rate $f_y$. Variables: $(a,b)$ is the fixed base point; $(x,y)$ is a nearby point where we evaluate the plane.

Q: Why does plugging $(x,y)=(a,b)$ into the tangent plane formula give $z=f(a,b)$?
A: The two linear correction terms vanish because $x-a=0$ and $y-b=0$. This confirms the plane passes through the point of tangency $(a,b,f(a,b))$, a necessary property of any tangent object.

## 8.3 Why the Plane Has the Correct Directional Slopes

Q: If you fix $y=b$ in the tangent plane $z=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$, what curve do you get and why is its slope $f_x(a,b)$?
A: Fixing $y=b$ kills the $y$-term, leaving $z=f(a,b)+f_x(a,b)(x-a)$, a line with slope $f_x(a,b)$ in the $xz$-plane. This matches the slope of the trace $z=f(x,b)$ at $x=a$, which is exactly the definition of $f_x(a,b)$.

Q: Why must the tangent plane's slope in the $y$-direction equal $f_y(a,b)$?
A: The trace on the surface obtained by fixing $x=a$ is the curve $z=f(a,y)$, whose slope at $y=b$ is $f_y(a,b)$ by definition. The tangent plane must contain the tangent line to this trace, so its $y$-slope must match $f_y(a,b)$.

C: The tangent plane to $z=f(x,y)$ at $(a,b)$ contains the tangent lines to both coordinate [traces] through that point.

## 8.4 Tangent Plane to a Level Surface

Q: For a level surface $F(x,y,z)=k$, why is $\nabla F(a,b,c)$ normal to the surface at $(a,b,c)$?
A: Along any curve lying in the level surface, $F$ is constant, so differentiating with the chain rule gives $\nabla F \cdot \mathbf{r}'(t)=0$. This means $\nabla F$ is perpendicular to every tangent vector at the point, hence normal to the surface. Variables: $F(x,y,z)$ is a scalar function; $\mathbf{r}(t)$ is any smooth curve on the surface; $k$ is a constant level value.

C: The tangent plane to the level surface $F(x,y,z)=k$ at $(a,b,c)$ has equation $F_x(a,b,c)(x-a) + F_y(a,b,c)(y-b) + [F_z(a,b,c)(z-c)] = 0$.

Q: Why does the tangent plane equation $\nabla F(a,b,c)\cdot\langle x-a,y-b,z-c\rangle=0$ make sense geometrically?
A: A plane is determined by a point and a normal vector. Here the point is $(a,b,c)$ on the surface, and $\nabla F(a,b,c)$ is the normal. The dot product being zero expresses that the displacement $\langle x-a,y-b,z-c\rangle$ to any point $(x,y,z)$ in the plane is perpendicular to that normal.

C: For the level surface form, the coefficients of $(x-a),(y-b),(z-c)$ in the tangent plane equation are the components of [the gradient $\nabla F(a,b,c)$].

## 8.5 Connecting the Graph Form and the Level Surface Form

Q: How does $z=f(x,y)$ fit into the level-surface framework $F(x,y,z)=k$?
A: Define $F(x,y,z)=f(x,y)-z$ and set $k=0$. Then $F=0$ exactly when $z=f(x,y)$, so the graph is the zero level surface of $F$. This lets you use gradient-based tangent plane methods on graphs too. Variables: $f(x,y)$ is the original function; $F(x,y,z)$ is the auxiliary three-variable function.

Q: Using $F(x,y,z)=f(x,y)-z$, what is $\nabla F$ and why does it recover the graph-form tangent plane?
A: $\nabla F = \langle f_x, f_y, -1\rangle$. The tangent plane equation $f_x(a,b)(x-a)+f_y(a,b)(y-b)-(z-c)=0$ with $c=f(a,b)$ rearranges to $z=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$, matching the graph formula exactly.

C: The graph $z=f(x,y)$ is the zero level set of $F(x,y,z)=[f(x,y)-z]$, and its normal vector is $\langle f_x,f_y,-1\rangle$.

## 8.6 Normal Line to a Surface

Q: What is the normal line to a surface at a point, and why is it useful?
A: It is the line through the point of tangency pointing in the direction of the surface's normal vector. It is useful for optics (reflection), geometry (perpendicularity constraints), and optimization (steepest ascent/descent directions). For a level surface at $(a,b,c)$, the normal direction is $\nabla F(a,b,c)$.

C: The normal line to $F(x,y,z)=k$ at $(a,b,c)$ has parametric form $(x,y,z)=(a,b,c)+t\,[\nabla F(a,b,c)]$, where $t\in\mathbb{R}$ is the line parameter.

Q: Why is the normal line perpendicular to the tangent plane at the same point?
A: Both use $\nabla F(a,b,c)$: the tangent plane takes it as its normal vector (perpendicular to the plane), while the normal line takes it as its direction vector. Any line whose direction equals a plane's normal is perpendicular to the plane.

## 8.7 Linearization of $f(x, y)$

C: The [linearization] of $f$ at $(a,b)$ is $L(x,y)=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$.

Q: What is the relationship between the linearization $L(x,y)$ and the tangent plane to $z=f(x,y)$?
A: They are the same thing in two different roles. The tangent plane is a geometric object in 3D; $L(x,y)$ is a scalar function of two variables whose graph is that plane. Writing $z=L(x,y)$ recovers the tangent plane equation.

Q: Why call $L(x,y)$ the "linearization" of $f$ at $(a,b)$?
A: Because $L$ is a linear (affine) function of $x$ and $y$ that matches $f$ and its first partial derivatives at $(a,b)$. It is the unique degree-1 polynomial in $(x-a)$ and $(y-b)$ with this matching property, so it is the linear function that best captures $f$'s local behavior.

## 8.8 Linear Approximation

C: For $(x,y)$ near $(a,b)$, the [linear approximation] states $f(x,y)\approx L(x,y)$, where $L$ is the linearization at $(a,b)$.

Q: Why is $f(x,y)\approx L(x,y)$ a useful approximation?
A: It replaces a potentially complicated function with a simple linear one, making arithmetic, error analysis, and sensitivity calculations tractable. The approximation is accurate whenever $(x,y)$ is close to $(a,b)$ and $f$ is differentiable there, since both $f$ and $L$ share value and first derivatives at $(a,b)$.

Q: How do you estimate $f(2.02, 2.97)$ using linearization at $(2,3)$?
A: Compute $L(x,y)=f(2,3)+f_x(2,3)(x-2)+f_y(2,3)(y-3)$, then plug in $x=2.02,y=2.97$. The small offsets $\Delta x=0.02,\Delta y=-0.03$ make the linear correction reliable. This is the 2D analogue of $f(a+h)\approx f(a)+f'(a)h$.

## 8.9 When Linear Approximation Is Reliable

Q: Why doesn't the mere existence of $f_x$ and $f_y$ at $(a,b)$ guarantee that $L(x,y)$ approximates $f(x,y)$ well?
A: Partial derivatives only measure change along the axes, not in diagonal directions. A function can have both partials exist yet fail to have a well-defined tangent plane (pathological examples exist where the surface has ridges). Reliable linear approximation requires the stronger condition of differentiability at $(a,b)$.

C: Linear approximation $f(x,y)\approx L(x,y)$ is reliable when $f$ is [differentiable] at $(a,b)$, which is guaranteed if $f_x$ and $f_y$ are continuous near $(a,b)$.

Q: What sufficient condition guarantees $f$ is differentiable at $(a,b)$?
A: If $f_x$ and $f_y$ both exist and are continuous in an open region containing $(a,b)$, then $f$ is differentiable there. This "continuously differentiable" condition is usually easy to check and is satisfied by virtually all elementary functions on their domains.

## 8.10 Differentials

C: The [total differential] of $z=f(x,y)$ is $dz=f_x(x,y)\,dx+f_y(x,y)\,dy$, where $dx,dy$ are independent differentials of the inputs.

Q: What is the difference between $\Delta z$ and $dz$?
A: $\Delta z = f(x+\Delta x, y+\Delta y)-f(x,y)$ is the true change in $z$. $dz=f_x\,dx+f_y\,dy$ is the linear prediction of that change using partial derivatives, where $dx=\Delta x, dy=\Delta y$. They agree exactly only for linear functions; otherwise $dz\approx\Delta z$ for small inputs.

Q: How does the differential formula $dz=f_x\,dx+f_y\,dy$ come from the linearization?
A: Starting from $L(x,y)=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$, subtract $f(a,b)$ and call the left side $dz$, with $dx=x-a,dy=y-b$. This gives $dz=f_x\,dx+f_y\,dy$, which says small input changes produce a linear combination of output changes weighted by partials.

## 8.11 Estimating Changes with Differentials

Q: Why use $dz\approx\Delta z$ instead of computing $\Delta z$ exactly?
A: Computing $\Delta z$ exactly often requires evaluating $f$ twice (at the new and old points), which may be expensive, numerically delicate, or impossible in symbolic form. The differential replaces one function evaluation and one subtraction with a single linear-combination formula involving known partials.

P: Use differentials to estimate $\Delta z$ for $z=f(x,y)=x^2 y$ when $(x,y)$ changes from $(3,1)$ to $(3.05,0.98)$.

S:
**IDENTIFY**: Approximate-change problem; use the total differential $dz=f_x\,dx+f_y\,dy$ at $(3,1)$.

**PLAN**:
- Compute $f_x,f_y$ symbolically.
- Evaluate partials at the base point $(3,1)$.
- Set $dx=0.05,dy=-0.02$ and plug in.

**EXECUTE**:
1. $f_x=2xy$, so $f_x(3,1)=6$.
2. $f_y=x^2$, so $f_y(3,1)=9$.
3. $dz=6(0.05)+9(-0.02)=0.30-0.18=0.12$.

**EVALUATE**: True $\Delta z=(3.05)^2(0.98)-9\approx 9.118-9=0.118$. The differential estimate $0.12$ matches to within $0.002$, confirming the linear approximation is reliable for these small changes.

## 8.12 Error Propagation

Q: How do differentials quantify how measurement errors propagate through a formula $z=f(x,y)$?
A: Treat $\Delta x,\Delta y$ as maximum measurement errors (in magnitude). Then the maximum propagated error is approximately $|\Delta z|\lesssim |f_x|\,|\Delta x|+|f_y|\,|\Delta y|$. Summing absolute values gives a worst-case bound because errors could align to reinforce each other.

C: In error propagation, the worst-case bound $|\Delta z|\le |f_x|\,|\Delta x|+|f_y|\,|\Delta y|$ uses [absolute values] because individual errors can be positive or negative and conspire additively.

Q: Why does relative error often matter more than absolute error in science and engineering?
A: A $1$ cm error matters differently for a $1$ m object (1%) than for a $10$ km object ($0.00001$%). Dividing through by $z$ gives the relative-error form $\tfrac{\Delta z}{z}\approx \tfrac{f_x}{z}\Delta x+\tfrac{f_y}{z}\Delta y$, which for products and powers often simplifies to a sum of fractional errors.

## 8.13 Linearization in Three or More Variables

C: The linearization of $w=f(x,y,z)$ at $(a,b,c)$ is $L(x,y,z)=f(a,b,c)+f_x(a,b,c)(x-a)+f_y(a,b,c)(y-b)+[f_z(a,b,c)(z-c)]$.

Q: Why does the linearization formula extend naturally to $n$ variables?
A: Because each partial derivative measures the rate of change in one independent direction, and for a differentiable function these contributions add linearly. In general, $L(\mathbf{x})=f(\mathbf{a})+\nabla f(\mathbf{a})\cdot(\mathbf{x}-\mathbf{a})$, where $\mathbf{x},\mathbf{a}\in\mathbb{R}^n$ and $\nabla f$ is the gradient.

C: In vector form, the linearization of $f$ at $\mathbf{a}\in\mathbb{R}^n$ is $L(\mathbf{x})=f(\mathbf{a})+[\nabla f(\mathbf{a})\cdot(\mathbf{x}-\mathbf{a})]$.

Q: What is the three-variable differential and how is it used for error propagation?
A: $dw=f_x\,dx+f_y\,dy+f_z\,dz$, summing contributions from each variable weighted by its partial. Worst-case error: $|\Delta w|\lesssim |f_x||\Delta x|+|f_y||\Delta y|+|f_z||\Delta z|$. This is essential for experimental sciences where multiple measurements combine.

## 8.14 Connection to Taylor Polynomials

Q: How is $L(x,y)$ the first-order Taylor polynomial of $f$ at $(a,b)$?
A: The Taylor expansion of $f$ about $(a,b)$ begins with $f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)+(\text{higher-order terms})$. Truncating after the linear terms gives exactly $L(x,y)$. So "linearization" is just "first-order Taylor approximation" under another name.

C: The linearization $L(x,y)$ is the [first-order Taylor polynomial] of $f$ centered at $(a,b)$.

Q: Why do we bother with higher-order Taylor polynomials if $L$ is easy and often good enough?
A: Linear approximation has error $O(|\mathbf{h}|^2)$, where $\mathbf{h}=(x-a,y-b)$. Quadratic and higher approximations reduce the error to $O(|\mathbf{h}|^3)$ or better, vital near critical points where $\nabla f=0$ and the linear term vanishes entirely.

## 8.15 Second-Order Taylor Expansion (Preview of Ch 9)

C: The second-order Taylor expansion of $f$ at $\mathbf{a}$ is $f(\mathbf{a}+\mathbf{h})\approx f(\mathbf{a})+\nabla f(\mathbf{a})\cdot\mathbf{h}+\tfrac{1}{2}\mathbf{h}^T [H(\mathbf{a})]\,\mathbf{h}$, where $H$ is the Hessian matrix of second partials and $\mathbf{h}=\mathbf{x}-\mathbf{a}$.

Q: What is the Hessian matrix $H$ and what does it encode?
A: For $f(x,y)$, $H=\begin{pmatrix}f_{xx} & f_{xy}\\ f_{yx} & f_{yy}\end{pmatrix}$, the matrix of second partial derivatives. It encodes curvature information: how the slope changes as you move in each direction. For mixed-partial-symmetric functions, $H$ is symmetric.

Q: Why is the Hessian crucial at critical points where $\nabla f=0$?
A: At such points the linear term vanishes, so $f(\mathbf{a}+\mathbf{h})\approx f(\mathbf{a})+\tfrac{1}{2}\mathbf{h}^T H\,\mathbf{h}$. The sign pattern of this quadratic form (determined by the Hessian's eigenvalues) tells you whether the point is a local min, local max, or saddle point — this is the content of the second-derivative test for multivariable optimization.

C: At a critical point, the [Hessian] determines whether the point is a local min, local max, or saddle point via its eigenvalue signs.

## 8.16 Worked Example: Tangent Plane to $z = x^2 + y^2$

P: Find the tangent plane to the surface $z=x^2+y^2$ at the point $(1,2,5)$.

S:
**IDENTIFY**: Tangent plane for a graph $z=f(x,y)$. Use $z=f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)$ with $(a,b)=(1,2)$.

**PLAN**:
- Verify $(1,2,5)$ lies on the surface.
- Compute partials $f_x,f_y$.
- Evaluate at $(1,2)$ and assemble the formula.

**EXECUTE**:
1. Check: $f(1,2)=1^2+2^2=5$. ✓
2. $f_x=2x\Rightarrow f_x(1,2)=2$.
3. $f_y=2y\Rightarrow f_y(1,2)=4$.
4. Tangent plane: $z=5+2(x-1)+4(y-2)$, simplifying to $z=2x+4y-5$.

**EVALUATE**: The surface is an upward-opening paraboloid, so the tangent plane should slope upward with a positive $x$- and $y$-slope, matching $2$ and $4$. Plugging in $(1,2)$ gives $z=2+8-5=5$, confirming the plane passes through the point of tangency.

## 8.17 Worked Example: Error Propagation in $V = \pi r^2 h$

P: A cylinder has radius $r=2$ (error $\pm 0.1$) and height $h=5$ (error $\pm 0.2$). Use differentials to estimate the maximum error in the computed volume $V=\pi r^2 h$.

S:
**IDENTIFY**: Error propagation problem. Use $dV=V_r\,dr+V_h\,dh$ with worst-case bound $|\Delta V|\lesssim |V_r|\,|\Delta r|+|V_h|\,|\Delta h|$.

**PLAN**:
- Compute $V_r=\partial V/\partial r$ and $V_h=\partial V/\partial h$.
- Evaluate at $(r,h)=(2,5)$.
- Sum absolute contributions using $|\Delta r|=0.1,|\Delta h|=0.2$.

**EXECUTE**:
1. $V_r = 2\pi r h$, so $V_r(2,5)=2\pi(2)(5)=20\pi$.
2. $V_h = \pi r^2$, so $V_h(2,5)=\pi(4)=4\pi$.
3. $|\Delta V|\le 20\pi(0.1)+4\pi(0.2)=2\pi+0.8\pi=2.8\pi\approx 8.80$.

**EVALUATE**: Nominal volume $V=\pi(4)(5)=20\pi\approx 62.83$, so the relative error is $\tfrac{2.8\pi}{20\pi}=14\%$. The radius dominates the error because $V$ depends on $r^2$: a 5% error in $r$ produces roughly a 10% error in $V$, confirming that squared quantities are especially sensitive to measurement uncertainty.
