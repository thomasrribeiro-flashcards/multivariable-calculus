+++
order = 12
tags = ["math", "multivariable-calculus", "change-of-variables", "jacobian", "transformations", "substitution"]
+++

# Multivariable Calculus — Change of Variables and the Jacobian

## 12.1 Motivating Problem

Q: Why do we bother with a change of variables in multiple integrals?
A: Some regions have awkward shapes (parallelograms, annuli, ellipses) and some integrands have awkward combinations (like $x+y$ or $x^2+y^2$). A well-chosen substitution can turn the region into a rectangle or the integrand into something separable, making the integral tractable. Without a substitution, many double and triple integrals are impossible in closed form.

Q: How is change of variables in double integrals analogous to single-variable $u$-substitution?
A: In single-variable calculus, $\int f(x)\,dx = \int f(g(u))g'(u)\,du$, where $g'(u)$ compensates for how $u$-substitution stretches/compresses the interval. In higher dimensions, the Jacobian determinant $|J|$ plays the role of $g'(u)$ — it compensates for how the transformation stretches area (or volume).

C: In a change of variables, the factor that accounts for how the transformation stretches area is called the [Jacobian].

Q: Before seeing the formula, predict: what should replace $g'(u)$ in the 2D change-of-variables rule $\iint_R f\,dA = \iint_S f(\cdot)\,?\,du\,dv$?
A: It should be a local area-scaling factor — something that measures how much a tiny patch in the $(u,v)$-plane stretches or shrinks when mapped into the $(x,y)$-plane. That factor turns out to be $|J|$, the absolute value of the Jacobian determinant.

## 12.2 Transformations $T:(u,v)\to(x,y)$

C: A 2D transformation $T$ is a pair of functions [$x = g(u,v)$ and $y = h(u,v)$] mapping points $(u,v)$ in one plane to points $(x,y)$ in another.

Q: In the notation $T:(u,v)\to(x,y)$ with $x=g(u,v),\,y=h(u,v)$, which variables are independent and which are dependent?
A: $(u,v)$ are the independent variables — the new coordinates we are integrating over. $(x,y)$ are the dependent variables — the original coordinates, expressed as functions of $u$ and $v$. The transformation sends each point of the $(u,v)$-plane to a point of the $(x,y)$-plane.

Q: If $T$ maps region $S$ in the $(u,v)$-plane onto region $R$ in the $(x,y)$-plane, what is the relationship between $S$ and $R$?
A: $R = T(S)$ is the image of $S$ under $T$. Every point of $R$ is the image of at least one point of $S$, and (for one-to-one $T$) exactly one point. We integrate $f(x,y)$ over $R$ but parametrize the computation using $(u,v)$ over $S$.

C: Polar coordinates are a transformation with $x = [r\cos\theta]$ and $y = [r\sin\theta]$.

## 12.3 One-to-One Transformations

Q: What does it mean for a transformation $T:(u,v)\to(x,y)$ to be one-to-one on a region $S$?
A: Distinct points in $S$ map to distinct points in $R=T(S)$: if $(u_1,v_1)\ne(u_2,v_2)$ in $S$, then $T(u_1,v_1)\ne T(u_2,v_2)$. This guarantees an inverse transformation exists on $R$, so we can unambiguously recover $(u,v)$ from $(x,y)$.

Q: Why is it usually enough for $T$ to be one-to-one only on the interior of $S$, not on the boundary?
A: The boundary of a 2D region has zero area, so multiple preimages on the boundary contribute nothing to the integral. For example, polar coordinates collapse the entire segment $r=0$ to a single point, but this boundary defect doesn't affect $\iint$.

C: For polar coordinates, $T$ fails to be one-to-one where [$r = 0$] because all angles $\theta$ map to the origin.

## 12.4 The Jacobian in 2D

C: The Jacobian of $T:(u,v)\to(x,y)$ is [$J = \frac{\partial(x,y)}{\partial(u,v)} = \det\begin{pmatrix} x_u & x_v\\ y_u & y_v\end{pmatrix}$], where subscripts denote partial derivatives.

Q: What is the explicit formula for the 2D Jacobian $J = \frac{\partial(x,y)}{\partial(u,v)}$?
A: $J = x_u y_v - x_v y_u$, where $x_u = \partial x/\partial u$, $x_v = \partial x/\partial v$, $y_u = \partial y/\partial u$, and $y_v = \partial y/\partial v$. It is the determinant of the matrix of first partials of $(x,y)$ with respect to $(u,v)$.

Q: Why is the Jacobian defined as a determinant rather than some other combination of partials?
A: The matrix of partials is the linearization (total derivative) of $T$ at a point. Its determinant gives the signed area of the image of the unit square under this linear map. Determinants are the natural measure of how linear maps scale volume.

Q: What goes wrong when the Jacobian vanishes at a point?
A: $J=0$ means the linearization is singular — it collapses area locally. The transformation is not locally invertible there and fails to be one-to-one in any neighborhood. Such points typically sit on the boundary of the region and can often be ignored.

## 12.5 Change-of-Variables Formula

C: The 2D change-of-variables formula is [$\iint_R f(x,y)\,dA = \iint_S f(x(u,v),y(u,v))\,|J|\,du\,dv$], where $S=T^{-1}(R)$ and $|J|$ is the absolute value of the Jacobian.

Q: In the formula $\iint_R f\,dA = \iint_S f(x(u,v),y(u,v))\,|J|\,du\,dv$, what four things must you do in practice?
A: (1) Rewrite $f(x,y)$ in terms of $u,v$ by substituting $x=g(u,v)$, $y=h(u,v)$. (2) Compute $J$ and take its absolute value. (3) Describe the new region $S$ in the $(u,v)$-plane. (4) Integrate the new integrand $f(\cdot)|J|$ over $S$.

Q: Why does $|J|$ appear inside the integral rather than as a constant factor outside?
A: The local stretching factor generally depends on where you are in the region — it is a function of $u$ and $v$, not a constant. Only for linear transformations does $J$ happen to be constant and pull out of the integral.

## 12.6 Why $|J|$ Appears

Q: Intuitively, why must $du\,dv$ be multiplied by $|J|$ to get the corresponding $dA$ in the $(x,y)$-plane?
A: $du\,dv$ measures area in the $(u,v)$-plane, but the transformation distorts area when it maps to the $(x,y)$-plane. The factor $|J|$ is the local area-scaling factor: a region of area $A_S$ in $(u,v)$ maps to a region of area approximately $|J|\cdot A_S$ in $(x,y)$. Without it, we'd be computing the wrong integral.

Q: If $|J| = 3$ at a point, what does that mean geometrically?
A: Near that point, the transformation locally magnifies area by a factor of 3: an infinitesimal patch of area $du\,dv$ in the $(u,v)$-plane corresponds to a patch of area $\approx 3\,du\,dv$ in the $(x,y)$-plane. The integrand must be weighted by 3 there to compensate.

Q: What would happen if we forgot the $|J|$ factor entirely?
A: We would get the wrong numerical answer — essentially we'd be integrating over $R$ as if it had the same area as $S$, which is false whenever $T$ is not area-preserving. The error is purely geometric: we'd miscount how much "real area" each $du\,dv$ patch represents.

## 12.7 Geometric Interpretation

Q: Geometrically, what is the image of an infinitesimal rectangle $[u, u+du]\times[v, v+dv]$ under a smooth transformation $T$?
A: To first order, its image is a parallelogram spanned by the two vectors $T_u\,du = (x_u, y_u)\,du$ and $T_v\,dv = (x_v, y_v)\,dv$. These are the partials of $T$ — tangent vectors along the $u$- and $v$-directions.

C: The area of the image parallelogram is [$|J|\,du\,dv$], the magnitude of the cross product of $T_u\,du$ and $T_v\,dv$.

Q: Why is the parallelogram's area exactly $|x_u y_v - x_v y_u|\,du\,dv$?
A: The area of a parallelogram with edge vectors $\vec a$ and $\vec b$ is $|\vec a\times\vec b|$. With $\vec a = (x_u, y_u, 0)du$ and $\vec b = (x_v, y_v, 0)dv$, the cross product's $z$-component is $(x_u y_v - x_v y_u)\,du\,dv$, whose magnitude is $|J|\,du\,dv$.

## 12.8 Deriving the Polar Jacobian

P: **Derive the Jacobian of the polar transformation** $x = r\cos\theta,\,y = r\sin\theta$.

S:
**IDENTIFY**: 2D Jacobian of a specific transformation $T:(r,\theta)\to(x,y)$.

**PLAN**: Compute the four partials, then the determinant
$J = \det\begin{pmatrix} x_r & x_\theta\\ y_r & y_\theta\end{pmatrix}$.

**EXECUTE**:
1. $x_r = \cos\theta$, $x_\theta = -r\sin\theta$.
2. $y_r = \sin\theta$, $y_\theta = r\cos\theta$.
3. $J = \cos\theta\cdot r\cos\theta - (-r\sin\theta)\cdot\sin\theta = r\cos^2\theta + r\sin^2\theta$.
4. Using $\cos^2\theta + \sin^2\theta = 1$: $J = r$.

**EVALUATE**: $J = r \ge 0$ on $r\ge 0$, so $|J|=r$ and $dA = r\,dr\,d\theta$, matching the familiar polar area element. At $r=0$ the Jacobian vanishes, reflecting the known degeneracy at the origin.

C: The polar-coordinate area element is $dA = [r]\,dr\,d\theta$.

## 12.9 3D Change of Variables

C: For a 3D transformation $x=g(u,v,w),\,y=h(u,v,w),\,z=k(u,v,w)$, the Jacobian is [$J = \det\begin{pmatrix} x_u & x_v & x_w\\ y_u & y_v & y_w\\ z_u & z_v & z_w\end{pmatrix}$].

C: The 3D change-of-variables formula is [$\iiint_R f\,dV = \iiint_S f(x,y,z)\,|J|\,du\,dv\,dw$], where $|J|$ is now a volume-scaling factor.

Q: Why is a $3\times 3$ determinant the right replacement for the $2\times 2$ Jacobian in three dimensions?
A: The determinant of an $n\times n$ matrix gives the signed $n$-dimensional volume of the image of the unit $n$-cube under the linear map. In 3D, the linearization of $T$ maps a tiny box $du\,dv\,dw$ to a parallelepiped whose volume is $|J|\,du\,dv\,dw$.

## 12.10 Cylindrical Jacobian

P: **Derive the Jacobian for cylindrical coordinates** $x=r\cos\theta,\,y=r\sin\theta,\,z=z$.

S:
**IDENTIFY**: 3D Jacobian with variables $(r,\theta,z)$.

**PLAN**: Build the $3\times 3$ matrix of partials and expand along the bottom row.

**EXECUTE**:
1. Partials: row 1 $(\cos\theta,-r\sin\theta,0)$; row 2 $(\sin\theta,r\cos\theta,0)$; row 3 $(0,0,1)$.
2. Expand along row 3: $J = 1\cdot\det\begin{pmatrix}\cos\theta & -r\sin\theta\\ \sin\theta & r\cos\theta\end{pmatrix}$.
3. $J = r\cos^2\theta + r\sin^2\theta = r$.

**EVALUATE**: Same factor $r$ as polar, which makes sense: the $z$-direction is unstretched, so only the planar $(r,\theta)\to(x,y)$ part scales area. Hence $dV = r\,dr\,d\theta\,dz$.

C: The cylindrical-coordinate volume element is $dV = [r]\,dr\,d\theta\,dz$.

## 12.11 Spherical Jacobian

C: For spherical coordinates $x=\rho\sin\phi\cos\theta,\,y=\rho\sin\phi\sin\theta,\,z=\rho\cos\phi$, the Jacobian is [$J = \rho^2\sin\phi$], where $\rho\ge 0$ is radial distance and $0\le\phi\le\pi$ is the polar angle from the $+z$-axis.

Q: Why does the spherical Jacobian have a $\rho^2$ factor?
A: A sphere of radius $\rho$ has surface area proportional to $\rho^2$. A thin spherical shell at radius $\rho$ has volume $\sim\rho^2 d\rho$, so each increment in $\rho$ contributes a surface patch that scales with $\rho^2$. The $\rho^2$ in $J$ captures exactly this radial area growth.

Q: Why does the spherical Jacobian have a $\sin\phi$ factor?
A: As $\phi$ moves from the poles ($\phi=0,\pi$) toward the equator ($\phi=\pi/2$), circles of constant latitude get larger. The circumference of such a circle is $2\pi\rho\sin\phi$, so the angular sweep $d\theta$ covers an arc length $\rho\sin\phi\,d\theta$. This introduces the $\sin\phi$ factor.

C: The spherical-coordinate volume element is $dV = [\rho^2\sin\phi]\,d\rho\,d\phi\,d\theta$.

Q: Why does the spherical Jacobian vanish at $\phi=0$ and $\phi=\pi$?
A: At the poles, the parametrization is degenerate: every value of $\theta$ gives the same point. This is the 3D analogue of the polar degeneracy at $r=0$. Because these sets have zero volume, the degeneracy doesn't affect the integral.

## 12.12 Linear Transformations

Q: What is special about the Jacobian of a linear transformation $T(u,v)=(au+bv,\,cu+dv)$?
A: Since $x,y$ are linear in $u,v$, the partials are constants: $x_u=a,\,x_v=b,\,y_u=c,\,y_v=d$. Hence $J = ad-bc$ is a constant — the determinant of the transformation matrix. It does not depend on $(u,v)$.

C: For a linear transformation with matrix $A = \begin{pmatrix}a & b\\ c & d\end{pmatrix}$, the Jacobian equals [$\det A = ad-bc$] everywhere.

Q: Why does a constant Jacobian make change of variables especially easy for linear transformations?
A: Because $|J|$ is constant, it pulls outside the integral: $\iint_R f\,dA = |J|\iint_S f(x(u,v),y(u,v))\,du\,dv$. The geometric picture is equally clean — the entire region $S$ is mapped to $R$ by the same uniform stretch factor.

## 12.13 Choosing a Substitution

Q: What are the two main clues that suggest a useful substitution?
A: (1) Symmetry in the integrand — expressions like $x+y$, $x-y$, $x^2+y^2$, or $x/y$ appearing repeatedly suggest naming them $u,v$. (2) Geometry of the region — regions bounded by lines like $x+y=c$ or curves like $xy=c$ simplify when those expressions become coordinate axes.

Q: Why should the substitution aim to straighten the region's boundary?
A: Integrals over rectangles are easier than integrals over slanted or curved regions. If the boundaries of $R$ are level curves of $u(x,y)$ and $v(x,y)$, then in $(u,v)$-coordinates $S$ becomes a rectangle, giving constant limits of integration.

Q: When both the integrand and the region suggest different substitutions, which usually wins?
A: Usually the region — awkward limits of integration are harder to work with than awkward integrands. Once the region is a rectangle, you can often deal with a complicated integrand. But ideally, one substitution simplifies both simultaneously.

## 12.14 Bounds Transformation

Q: Why must you re-express the region, not just the integrand, when changing variables?
A: The integral $\iint_S \cdots\,du\,dv$ requires limits on $u$ and $v$. Those limits describe $S=T^{-1}(R)$ in the $(u,v)$-plane, not $R$ in the $(x,y)$-plane. Forgetting this step gives the right integrand but the wrong region, and therefore the wrong answer.

Q: How do you translate a boundary curve of $R$ into the $(u,v)$-plane?
A: Substitute $u(x,y)$ and $v(x,y)$ into the boundary equation. For example, the line $x+y=1$ under $u=x+y,\,v=x-y$ becomes $u=1$, a vertical line in the $(u,v)$-plane. Each boundary curve of $R$ becomes a boundary curve of $S$.

Q: How do you tell whether $S$ should be described by $u$ or $v$ as outer variable?
A: Look at the shape of $S$. If $S$ is bounded above and below by horizontal lines $v=v_{\min}$ and $v=v_{\max}$, and left/right by curves $u=u_1(v),\,u=u_2(v)$, integrate $u$ first, then $v$. Sketching $S$ is crucial — don't rely on the shape of $R$.

## 12.15 Common Transformations

C: The substitution $u=x+y,\,v=x-y$ is useful for regions bounded by [lines of slope $\pm 1$] and integrands involving $x+y$ or $x-y$.

C: The substitution $u=x/y,\,v=xy$ is useful for regions bounded by [hyperbolas $xy=c$] and lines through the origin.

Q: What region does $u = x/a$, $v = y/b$ turn an ellipse $x^2/a^2+y^2/b^2=1$ into?
A: The unit disk $u^2+v^2\le 1$. The Jacobian of $(u,v)\to(x,y)$ — i.e., $x=au,\,y=bv$ — is $ab$, so $dA = ab\,du\,dv$. This is the standard trick for integrating over ellipses.

Q: Why is $u=x+y,\,v=x-y$ natural for integrands like $(x-y)^2/(x+y)$?
A: Both $x-y$ and $x+y$ become single coordinate variables ($v$ and $u$), so the integrand becomes $v^2/u$ — completely separable in $u$ and $v$. This is the whole point of matching the substitution to the integrand's symmetry.

## 12.16 Inverting the Transformation

Q: If you are given $u,v$ as functions of $x,y$ but the formula needs $x,y$ as functions of $u,v$, what must you do first?
A: Solve the system $u=u(x,y),\,v=v(x,y)$ for $x$ and $y$ in terms of $u$ and $v$. The change-of-variables formula requires expressing $f$ and computing partials of $x,y$ with respect to $u,v$, so the inversion is a prerequisite step.

Q: Is there a shortcut when inverting is hard?
A: Yes: compute the "reverse" Jacobian $\frac{\partial(u,v)}{\partial(x,y)}$ directly from the given formulas, then use the identity $\frac{\partial(x,y)}{\partial(u,v)} = \left(\frac{\partial(u,v)}{\partial(x,y)}\right)^{-1}$. This lets you find $|J|$ without explicitly inverting the transformation.

C: The Jacobians of a transformation and its inverse satisfy $\frac{\partial(x,y)}{\partial(u,v)}\cdot\frac{\partial(u,v)}{\partial(x,y)} = [1]$.

## 12.17 Orientation and Absolute Value

Q: Why do we use $|J|$, not $J$, in the change-of-variables formula for area/volume?
A: The signed determinant $J$ detects orientation — whether $T$ preserves or reverses orientation. Areas and volumes are unsigned quantities, so we take $|J|$. If we want oriented integrals (e.g., line or surface integrals with orientation), the sign matters.

Q: What does $J<0$ mean geometrically?
A: The transformation reverses orientation locally — like a reflection. A counterclockwise loop in the $(u,v)$-plane maps to a clockwise loop in the $(x,y)$-plane. The magnitude $|J|$ still gives the correct area-scaling factor; only the sign flips.

## 12.18 P:/S: Parallelogram via $u=x+y,\,v=x-y$

P: **Evaluate** $\iint_R (x-y)^2\,dA$, where $R$ is the parallelogram with vertices $(0,0),\,(1,1),\,(2,0),\,(1,-1)$, using the substitution $u=x+y,\,v=x-y$.

S:
**IDENTIFY**: Double integral over a tilted parallelogram whose sides have slopes $\pm 1$; integrand depends on $x-y$. Perfect match for $u=x+y,\,v=x-y$.

**PLAN**:
- Invert: solve for $x,y$ in terms of $u,v$.
- Transform the four vertices to find $S$.
- Compute the Jacobian.
- Write and evaluate the new integral.

**EXECUTE**:
1. Invert: adding and subtracting gives $x = (u+v)/2$, $y = (u-v)/2$.
2. Transform vertices:
   - $(0,0)\to (u,v)=(0,0)$.
   - $(1,1)\to (2,0)$.
   - $(2,0)\to (2,2)$.
   - $(1,-1)\to (0,2)$.
   So $S$ is the square $0\le u\le 2,\,0\le v\le 2$.
3. Jacobian: $x_u=\tfrac12,\,x_v=\tfrac12,\,y_u=\tfrac12,\,y_v=-\tfrac12$, so $J = \tfrac12\cdot(-\tfrac12) - \tfrac12\cdot\tfrac12 = -\tfrac12$. Hence $|J|=\tfrac12$.
4. Integrand: $(x-y)^2 = v^2$.
5. Integral: $\iint_R (x-y)^2\,dA = \int_0^2\!\int_0^2 v^2\cdot\tfrac12\,du\,dv = \tfrac12\int_0^2 2v^2\,dv = \int_0^2 v^2\,dv = \tfrac{8}{3}$.

**EVALUATE**: The parallelogram has area $2\cdot 2\cdot\tfrac12 = 2$ (check: determinant of edge vectors $(1,1)$ and $(1,-1)$ gives $|-2|=2$), and $(x-y)^2$ ranges from $0$ to $4$, so an average value around $\tfrac{4}{3}$ gives $\tfrac{4}{3}\cdot 2 = \tfrac{8}{3}$. The answer is physically reasonable.

## 12.19 P:/S: Ball Integral via Spherical Coordinates

P: **Compute** $\iiint_E (x^2+y^2+z^2)\,dV$, where $E$ is the ball of radius $2$ centered at the origin, using spherical coordinates.

S:
**IDENTIFY**: Triple integral over a ball with integrand $x^2+y^2+z^2 = \rho^2$. Spherical coordinates will make both the region and the integrand trivial.

**PLAN**:
- Use $x=\rho\sin\phi\cos\theta$, $y=\rho\sin\phi\sin\theta$, $z=\rho\cos\phi$, so $x^2+y^2+z^2=\rho^2$.
- Region: $0\le\rho\le 2$, $0\le\phi\le\pi$, $0\le\theta\le 2\pi$.
- Use $dV = \rho^2\sin\phi\,d\rho\,d\phi\,d\theta$.
- Separate the integral into three 1D integrals.

**EXECUTE**:
1. Rewrite: $\iiint_E \rho^2\cdot\rho^2\sin\phi\,d\rho\,d\phi\,d\theta = \int_0^{2\pi}\!\int_0^{\pi}\!\int_0^2 \rho^4\sin\phi\,d\rho\,d\phi\,d\theta$.
2. $\int_0^2 \rho^4\,d\rho = \tfrac{32}{5}$.
3. $\int_0^{\pi}\sin\phi\,d\phi = [-\cos\phi]_0^{\pi} = 2$.
4. $\int_0^{2\pi}d\theta = 2\pi$.
5. Multiply: $\tfrac{32}{5}\cdot 2\cdot 2\pi = \tfrac{128\pi}{5}$.

**EVALUATE**: The ball has volume $\tfrac{4}{3}\pi(2)^3 = \tfrac{32\pi}{3}$, and $\rho^2$ averages $\tfrac{1}{V}\int_E\rho^2\,dV$. Our answer gives an average of $\tfrac{128\pi/5}{32\pi/3} = \tfrac{12}{5} = 2.4$, which is less than the maximum value $\rho^2=4$ at the boundary and greater than zero at the center — reasonable for a weighted average. Units and signs check out.
