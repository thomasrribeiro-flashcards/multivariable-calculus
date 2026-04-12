+++
order = 7
tags = ["math", "multivariable-calculus", "chain-rule", "gradient", "directional-derivative", "implicit-differentiation"]
+++

# Multivariable Calculus — Chain Rule, Directional Derivatives, and the Gradient

## 7.1 Why the chain rule generalizes to multiple variables

Q: Why does the single-variable chain rule need a generalization when we move to multivariable calculus?
A: In one variable, a composition $f(g(t))$ has only one pathway for $t$ to influence the output, so $df/dt = f'(g)\,g'(t)$. With multiple inputs, changing one underlying variable (say $t$) can affect the output through several intermediate variables simultaneously — for example, $z = f(x(t), y(t))$ routes $t$'s influence through both $x$ and $y$. We need a rule that sums the contributions from every independent pathway.

Q: Conceptually, what does the multivariable chain rule express about how a change propagates through a composition?
A: It expresses a total rate of change as a sum over all routes: each intermediate variable contributes its partial sensitivity (how $f$ responds to it) times the rate at which that intermediate changes. The linearization of $f$ is applied along the velocity vector of the intermediate variables, so the rule is essentially "total change = dot product of sensitivities with input rates."

Q: Before seeing the formula, predict: if $z = f(x, y)$ and both $x$ and $y$ depend on $t$, why might $dz/dt$ involve both $f_x$ and $f_y$?
A: Because $t$ changes $x$ at rate $dx/dt$ and changes $y$ at rate $dy/dt$, and $f$ responds to each input with its own sensitivity ($f_x$ and $f_y$). The total rate of change of $z$ is the sum of these two contributions, since both routes are happening at once.

C: The multivariable chain rule generalizes the single-variable version by [summing contributions from every intermediate pathway], because each independent variable can influence the output through multiple intermediate variables.

## 7.2 Chain rule for $z = f(x(t), y(t))$

Q: State the chain rule for $z = f(x(t), y(t))$ and explain each symbol.
A: $\dfrac{dz}{dt} = f_x\,\dfrac{dx}{dt} + f_y\,\dfrac{dy}{dt}$, where $f_x = \partial f/\partial x$ and $f_y = \partial f/\partial y$ are partial derivatives of $f$ evaluated at $(x(t), y(t))$, and $dx/dt$, $dy/dt$ are the rates of change of the intermediates with respect to $t$. The result $dz/dt$ is a total (not partial) derivative because $t$ is the only independent variable.

Q: Why is $dz/dt$ written as a total derivative (using $d$) rather than a partial $\partial z/\partial t$ in the rule $dz/dt = f_x\,dx/dt + f_y\,dy/dt$?
A: Because once we fix the paths $x(t)$ and $y(t)$, $z$ becomes a function of the single variable $t$, so there is nothing else to hold fixed. Partials are reserved for situations where multiple independent variables coexist.

C: For $z = f(x(t), y(t))$, the chain rule gives [$dz/dt = f_x\,dx/dt + f_y\,dy/dt$], where $f_x$ and $f_y$ are evaluated along the curve $(x(t), y(t))$.

Q: If $z = x^2 y$ with $x(t) = \cos t$ and $y(t) = \sin t$, what is $dz/dt$ in terms of $t$?
A: $f_x = 2xy$, $f_y = x^2$, $dx/dt = -\sin t$, $dy/dt = \cos t$. Then $dz/dt = 2xy(-\sin t) + x^2(\cos t) = -2\cos t\sin^2 t + \cos^3 t$.

## 7.3 Chain rule for $z = f(x(s, t), y(s, t))$

Q: How does the chain rule change when the intermediates $x$ and $y$ depend on two independent variables $s$ and $t$?
A: Each independent variable gets its own chain rule. We use partial derivatives because now both $s$ and $t$ are independent: $\dfrac{\partial z}{\partial s} = f_x\,\dfrac{\partial x}{\partial s} + f_y\,\dfrac{\partial y}{\partial s}$ and $\dfrac{\partial z}{\partial t} = f_x\,\dfrac{\partial x}{\partial t} + f_y\,\dfrac{\partial y}{\partial t}$. The structure is identical — sum contributions along all paths — but $s$ and $t$ each get their own sum.

C: For $z = f(x(s, t), y(s, t))$, [$\partial z/\partial s = f_x\,\partial x/\partial s + f_y\,\partial y/\partial s$], where all partials of $f$ are evaluated at $(x(s, t), y(s, t))$.

Q: Why must we switch from $d$ to $\partial$ when $x$ and $y$ depend on more than one variable?
A: Because with multiple independent inputs ($s$ and $t$), differentiating with respect to one requires holding the others fixed. The partial notation records which variable is being varied and which are held constant, which is ambiguous with $d$.

## 7.4 Tree diagrams as a bookkeeping device

Q: What is a "tree diagram" in the context of the multivariable chain rule, and why is it useful?
A: A tree diagram is a visual graph with the dependent variable at the top, intermediate variables in the middle, and independent variables at the bottom, with edges labeled by the corresponding partial derivatives. To differentiate with respect to an independent variable, you sum over all root-to-leaf paths, multiplying the derivatives along each path. It turns the chain rule into a mechanical "paths × products" procedure, making errors less likely.

Q: How does a tree diagram encode the rule $dz/dt = f_x\,dx/dt + f_y\,dy/dt$?
A: $z$ sits at the root with two children $x$ and $y$ (labeled $f_x$ and $f_y$). Each of $x$ and $y$ has one child $t$ (labeled $dx/dt$ and $dy/dt$). Two root-to-leaf paths exist: $z \to x \to t$ gives $f_x\,dx/dt$, and $z \to y \to t$ gives $f_y\,dy/dt$. Summing these gives the rule.

C: In a tree diagram, differentiating with respect to an independent variable means [summing over all root-to-leaf paths], multiplying the partial derivatives labeling the edges along each path.

## 7.5 Implicit differentiation from the chain rule (two variables)

Q: If an equation $F(x, y) = 0$ implicitly defines $y$ as a function of $x$, how does the chain rule give a formula for $dy/dx$?
A: Differentiate both sides with respect to $x$, treating $y$ as $y(x)$. The chain rule gives $F_x + F_y\,(dy/dx) = 0$. Solving yields $\dfrac{dy}{dx} = -\dfrac{F_x}{F_y}$ (valid wherever $F_y \ne 0$). This avoids having to solve $F(x, y) = 0$ explicitly for $y$.

C: For $F(x, y) = 0$ with $F_y \ne 0$, implicit differentiation gives [$dy/dx = -F_x/F_y$], where $F_x$ and $F_y$ are partial derivatives of $F$.

Q: Why is the condition $F_y \ne 0$ necessary for the implicit formula $dy/dx = -F_x/F_y$?
A: Division by $F_y$ is only defined when $F_y \ne 0$. Geometrically, $F_y = 0$ means the level curve has a vertical tangent at that point, so $y$ is not locally expressible as a differentiable function of $x$. This is the condition required by the implicit function theorem.

## 7.6 Implicit differentiation for $F(x, y, z) = 0$

Q: If $F(x, y, z) = 0$ defines $z$ implicitly as a function of $x$ and $y$, what is $\partial z/\partial x$?
A: Differentiating the equation with respect to $x$ while treating $y$ as fixed and $z = z(x, y)$, the chain rule gives $F_x + F_z\,(\partial z/\partial x) = 0$, so $\dfrac{\partial z}{\partial x} = -\dfrac{F_x}{F_z}$ (assuming $F_z \ne 0$). By symmetry, $\partial z/\partial y = -F_y/F_z$.

C: For $F(x, y, z) = 0$ defining $z = z(x, y)$, [$\partial z/\partial x = -F_x/F_z$] when $F_z \ne 0$.

Q: Why is the form $\partial z/\partial x = -F_x/F_z$ strictly parallel to the two-variable version $dy/dx = -F_x/F_y$?
A: In both cases the "bottom" variable is the one being solved for, and we differentiate $F = 0$ with respect to the target independent variable. The rule is always: minus the partial with respect to the independent variable, divided by the partial with respect to the dependent variable.

## 7.7 The gradient vector

Q: What is the gradient of a scalar function $f$, and why is it defined as a vector?
A: The gradient $\nabla f$ is the vector of all first partial derivatives: $\nabla f = \langle f_x, f_y\rangle$ in 2D or $\nabla f = \langle f_x, f_y, f_z\rangle$ in 3D. Packaging the partials as a vector lets us describe directional information (rates of change along arbitrary directions, steepest ascent, perpendicularity to level sets) using vector operations like the dot product.

C: In three dimensions, the gradient of $f(x, y, z)$ is [$\nabla f = \langle f_x, f_y, f_z\rangle$], the vector whose components are the partial derivatives of $f$.

Q: How are the units/meaning of each component of $\nabla f$ interpreted?
A: Each component is a rate of change of $f$ per unit change in one coordinate direction, with the other coordinates held fixed. So $f_x$ says "how fast $f$ grows per unit motion in $x$"; the whole vector encodes how $f$ responds to each coordinate direction simultaneously.

## 7.8 Chain rule in gradient form

Q: How can the chain rule for a curve $\vec{r}(t) = (x(t), y(t), z(t))$ be written compactly using the gradient?
A: $\dfrac{d}{dt}f(\vec{r}(t)) = \nabla f(\vec{r}(t))\cdot\vec{r}\,'(t)$, where $\vec{r}\,'(t) = \langle dx/dt, dy/dt, dz/dt\rangle$ is the velocity vector. This rewrites the sum $f_x\,dx/dt + f_y\,dy/dt + f_z\,dz/dt$ as a dot product of the gradient with the velocity.

C: Along a curve $\vec{r}(t)$, the chain rule reads [$\frac{d}{dt}f(\vec{r}(t)) = \nabla f\cdot\vec{r}\,'(t)$], where $\vec{r}\,'(t)$ is the velocity vector of the curve.

Q: Why is the gradient form of the chain rule conceptually powerful, beyond just being compact?
A: It separates the geometry of $f$ (its gradient, which depends only on $f$ and position) from the geometry of the path ($\vec{r}\,'(t)$, which depends only on the curve). The rate of change of $f$ along the path is then just the projection of the motion onto the gradient direction — a purely geometric statement.

## 7.9 Directional derivative

Q: What is the directional derivative $D_{\vec{u}} f(\vec{x}_0)$, and why do we require $\vec{u}$ to be a unit vector?
A: $D_{\vec{u}} f(\vec{x}_0)$ is the instantaneous rate of change of $f$ at $\vec{x}_0$ as one moves in the direction $\vec{u}$. Formally, $D_{\vec{u}} f(\vec{x}_0) = \lim_{h \to 0} \dfrac{f(\vec{x}_0 + h\vec{u}) - f(\vec{x}_0)}{h}$. Requiring $|\vec{u}| = 1$ ensures $h$ measures actual distance traveled, so the derivative has units of "change in $f$ per unit length" rather than being scaled by the magnitude of $\vec{u}$.

C: The directional derivative $D_{\vec{u}} f(\vec{x}_0)$ measures the rate of change of $f$ at $\vec{x}_0$ [in the direction of the unit vector $\vec{u}$].

Q: What would happen if we dropped the unit-vector requirement and used an arbitrary $\vec{u}$ in the directional derivative formula?
A: The value would scale with $|\vec{u}|$, so doubling $\vec{u}$ would double the "derivative" even though the direction is identical. This defeats the purpose — we want a number that depends only on direction, not on how we parametrize it. Normalizing to a unit vector removes this ambiguity.

## 7.10 Directional derivative formula

Q: How is the directional derivative computed from the gradient?
A: $D_{\vec{u}} f(\vec{x}_0) = \nabla f(\vec{x}_0)\cdot\vec{u}$, provided $\vec{u}$ is a unit vector. This follows from the chain rule: moving along the line $\vec{r}(t) = \vec{x}_0 + t\vec{u}$ gives $\vec{r}\,'(t) = \vec{u}$, so $d/dt\,f(\vec{r}(t))|_{t=0} = \nabla f\cdot\vec{u}$.

C: The directional derivative formula is [$D_{\vec{u}} f = \nabla f\cdot\vec{u}$], where $\vec{u}$ must be a unit vector.

Q: If someone hands you a non-unit direction vector $\vec{v}$ and asks for the directional derivative of $f$ "in the direction of $\vec{v}$," what must you do first?
A: Normalize: let $\vec{u} = \vec{v}/|\vec{v}|$, then compute $D_{\vec{u}} f = \nabla f\cdot(\vec{v}/|\vec{v}|)$. Forgetting to normalize gives a value scaled by $|\vec{v}|$, which is wrong.

## 7.11 Partial derivatives as special directional derivatives

Q: Why are partial derivatives $f_x$, $f_y$, $f_z$ just special cases of the directional derivative?
A: They are directional derivatives along the coordinate axes. Taking $\vec{u} = \hat{\imath} = \langle 1, 0, 0\rangle$, the formula $D_{\vec{u}} f = \nabla f\cdot\vec{u}$ picks off the first component: $\nabla f\cdot\hat{\imath} = f_x$. Similarly $\hat{\jmath}$ gives $f_y$ and $\hat{k}$ gives $f_z$. So partials measure change along axis directions; the directional derivative generalizes this to any direction.

C: The partial derivative $f_x$ is the directional derivative of $f$ along [the unit vector $\hat{\imath}$], the $x$-axis direction.

Q: Why is it conceptually important that partials are just one choice of direction among infinitely many?
A: It shows that partial derivatives alone don't fully capture how $f$ varies at a point — they only describe change along a handful of privileged directions. The gradient, built from these partials, encodes the complete first-order behavior and lets you recover the rate in any direction via a dot product.

## 7.12 Direction of maximum increase

Q: In what direction does $f$ increase most rapidly at a point $\vec{x}_0$, and what is the maximum rate?
A: Since $D_{\vec{u}} f = \nabla f\cdot\vec{u} = |\nabla f|\,|\vec{u}|\cos\theta = |\nabla f|\cos\theta$ (with $|\vec{u}| = 1$), the value is maximized when $\cos\theta = 1$, i.e., $\vec{u}$ points in the same direction as $\nabla f$. The direction of steepest ascent is $\vec{u} = \nabla f/|\nabla f|$, and the maximum rate is $|\nabla f|$.

C: At a point where $\nabla f \ne \vec{0}$, the direction of maximum increase of $f$ is [$\vec{u} = \nabla f/|\nabla f|$], and the maximum rate is $|\nabla f|$.

Q: Why does the maximum rate of change of $f$ equal the magnitude of the gradient?
A: Because $D_{\vec{u}} f = |\nabla f|\cos\theta$ with $\theta$ the angle between $\vec{u}$ and $\nabla f$. The maximum of $\cos\theta$ is $1$, achieved when $\vec{u}$ aligns with $\nabla f$, giving $D_{\vec{u}} f = |\nabla f|$. So the gradient's length literally measures how quickly $f$ can change per unit distance.

## 7.13 Direction of maximum decrease

Q: In what direction does $f$ decrease most rapidly, and what is the minimum rate?
A: The minimum of $\cos\theta$ is $-1$, achieved when $\vec{u}$ points opposite to $\nabla f$. So the direction of steepest descent is $\vec{u} = -\nabla f/|\nabla f|$, giving minimum rate $-|\nabla f|$ (the most negative value of any directional derivative at that point).

C: The direction of steepest descent of $f$ is [$-\nabla f/|\nabla f|$], and the most negative directional derivative at a point is $-|\nabla f|$.

Q: Why, at a regular point ($\nabla f \ne \vec{0}$), is there also a direction in which $f$ has zero rate of change?
A: Any $\vec{u}$ perpendicular to $\nabla f$ gives $D_{\vec{u}} f = \nabla f\cdot\vec{u} = 0$. Geometrically, such directions lie in the tangent space to the level set of $f$ through that point, and moving tangent to a level set keeps $f$ constant to first order.

## 7.14 Gradient is perpendicular to level sets

Q: What is the relationship between $\nabla f$ and the level curves (or level surfaces) of $f$?
A: $\nabla f(\vec{x}_0)$ is perpendicular to the level set of $f$ passing through $\vec{x}_0$. In 2D, it is normal to the level curve $f(x, y) = c$; in 3D, it is normal to the level surface $f(x, y, z) = c$. This is the geometric interpretation of the gradient: it points "uphill," perpendicular to contours of constant value.

C: At any regular point, $\nabla f$ is [perpendicular to the level set] of $f$ through that point.

Q: Why does knowing $\nabla f \perp$ level set give us the direction of steepest ascent for free?
A: Because motion tangent to the level set leaves $f$ unchanged, the only way to change $f$ is to move with some component perpendicular to the level set. Since $\nabla f$ is that perpendicular direction and points where $f$ grows, steepest ascent must lie along $\nabla f$.

## 7.15 Why the gradient is perpendicular to level sets

Q: Using the chain rule, explain why $\nabla f$ is perpendicular to any curve lying in a level set of $f$.
A: Let $\vec{r}(t)$ be any smooth curve lying on the level set $f(\vec{x}) = c$, so $f(\vec{r}(t)) = c$ for all $t$. Differentiating both sides with respect to $t$ gives $\nabla f\cdot\vec{r}\,'(t) = 0$. Since $\vec{r}\,'(t)$ is an arbitrary tangent vector to the level set, $\nabla f$ is orthogonal to every tangent direction, hence perpendicular to the level set itself.

C: Because $f(\vec{r}(t))$ is constant along a level-set curve, differentiating gives [$\nabla f\cdot\vec{r}\,'(t) = 0$], so $\nabla f$ is perpendicular to every tangent vector of the level set.

Q: Before seeing the proof, predict: why might moving along a level curve keep $f$ constant, and what does that say about the dot product $\nabla f\cdot\vec{v}$ for tangent $\vec{v}$?
A: By definition a level curve is where $f$ equals a fixed value, so motion along it cannot change $f$. The rate of change along the curve is $\nabla f\cdot\vec{v}$, which must therefore be zero — forcing $\nabla f \perp \vec{v}$ for every tangent $\vec{v}$.

## 7.16 Applications: steepest ascent/descent and physics

Q: How is the gradient used in optimization algorithms like gradient descent?
A: To minimize a function $f$, you take steps in the direction of steepest descent $-\nabla f$, because this is the direction along which $f$ decreases fastest per unit distance. Iteratively updating $\vec{x}_{k+1} = \vec{x}_k - \alpha\,\nabla f(\vec{x}_k)$ (with step size $\alpha > 0$) converges, under suitable conditions, to a local minimum. Steepest ascent analogously maximizes by stepping along $+\nabla f$.

Q: In physics, why is a conservative force written as $\vec{F} = -\nabla U$, where $U$ is potential energy?
A: A conservative force does work that depends only on endpoints, and this is captured by saying the force field is the negative gradient of a scalar potential $U$. The minus sign encodes that forces push objects toward lower potential energy — e.g., gravity pulls you "downhill" on the potential surface, which is the direction of steepest descent of $U$.

C: A conservative force field is expressed as [$\vec{F} = -\nabla U$], where $U$ is the potential energy, so the force points in the direction of steepest decrease of $U$.

Q: Why does the relationship $\vec{F} = -\nabla U$ automatically imply that $\vec{F}$ is perpendicular to equipotential surfaces?
A: Equipotential surfaces are level surfaces of $U$, and $\nabla U$ is perpendicular to them (from the gradient/level-set theorem). Since $\vec{F} = -\nabla U$ is just the opposite vector, $\vec{F}$ is also perpendicular to equipotentials — which is why, e.g., electric field lines meet equipotentials at right angles.

## 7.17 Tangent plane to a level surface

Q: How do you find the tangent plane to a level surface $F(x, y, z) = k$ at a point $\vec{x}_0 = (x_0, y_0, z_0)$?
A: The gradient $\nabla F(\vec{x}_0)$ is perpendicular to the level surface at $\vec{x}_0$, so it serves as a normal vector to the tangent plane. Using the point-normal form, the plane is $\nabla F(\vec{x}_0)\cdot\langle x - x_0, y - y_0, z - z_0\rangle = 0$, or equivalently $F_x(\vec{x}_0)(x - x_0) + F_y(\vec{x}_0)(y - y_0) + F_z(\vec{x}_0)(z - z_0) = 0$.

C: The tangent plane to $F(x, y, z) = k$ at $\vec{x}_0$ has [$\nabla F(\vec{x}_0)$ as a normal vector], giving the equation $\nabla F(\vec{x}_0)\cdot(\vec{x} - \vec{x}_0) = 0$.

Q: Why is using the gradient as a normal vector often easier than the explicit tangent-plane formula $z = f(x_0, y_0) + f_x\Delta x + f_y\Delta y$?
A: The gradient-normal method works directly for implicit surfaces like $x^2 + y^2 + z^2 = R^2$, where no single variable can easily be solved for as a function of the others. The explicit formula requires expressing $z = f(x, y)$; the gradient method treats $x$, $y$, $z$ symmetrically and needs only one partial-derivative calculation per variable.

## 7.18 Procedural: partials via chain rule with two intermediates

P: Given $z = x^2 + y^2$, $x = s + t$, $y = s - t$, find $\partial z/\partial s$ and $\partial z/\partial t$.

S:
**IDENTIFY**: Chain-rule problem with two independent variables ($s$, $t$) and two intermediate variables ($x$, $y$). We need partial derivatives $\partial z/\partial s$ and $\partial z/\partial t$ using the formula $\partial z/\partial s = f_x\,\partial x/\partial s + f_y\,\partial y/\partial s$ and similarly for $t$.

**PLAN**:
- Compute $f_x = \partial z/\partial x$ and $f_y = \partial z/\partial y$ from $z = x^2 + y^2$.
- Compute $\partial x/\partial s$, $\partial x/\partial t$, $\partial y/\partial s$, $\partial y/\partial t$ from the linear substitutions.
- Apply the chain rule twice (once for $s$, once for $t$) and simplify to a function of $s$ and $t$.

**EXECUTE**:
1. $f_x = 2x$, $f_y = 2y$.
2. From $x = s + t$: $\partial x/\partial s = 1$, $\partial x/\partial t = 1$. From $y = s - t$: $\partial y/\partial s = 1$, $\partial y/\partial t = -1$.
3. $\partial z/\partial s = 2x(1) + 2y(1) = 2(x + y) = 2(2s) = 4s$.
4. $\partial z/\partial t = 2x(1) + 2y(-1) = 2(x - y) = 2(2t) = 4t$.

**EVALUATE**: As a sanity check, substitute directly: $z = (s+t)^2 + (s-t)^2 = 2s^2 + 2t^2$. Differentiating gives $\partial z/\partial s = 4s$ and $\partial z/\partial t = 4t$, matching the chain-rule result. The answers are linear in $s$ and $t$ as expected from a quadratic $z$.

## 7.19 Procedural: direction and rate of maximum increase

P: Find the direction of maximum increase of $f(x, y) = x e^y$ at the point $(2, 0)$, and the rate of increase in that direction.

S:
**IDENTIFY**: Gradient/directional-derivative problem. The direction of maximum increase is $\nabla f/|\nabla f|$, and the maximum rate of increase is $|\nabla f|$, both evaluated at $(2, 0)$.

**PLAN**:
- Compute partial derivatives $f_x$ and $f_y$ of $f(x, y) = x e^y$.
- Evaluate $\nabla f$ at $(2, 0)$.
- Report the direction as the unit vector $\nabla f/|\nabla f|$.
- Report the maximum rate as $|\nabla f|$.

**EXECUTE**:
1. $f_x = \partial/\partial x\,(x e^y) = e^y$ and $f_y = \partial/\partial y\,(x e^y) = x e^y$.
2. At $(2, 0)$: $e^0 = 1$, so $f_x(2, 0) = 1$ and $f_y(2, 0) = 2\cdot 1 = 2$. Thus $\nabla f(2, 0) = \langle 1, 2\rangle$.
3. Magnitude: $|\nabla f| = \sqrt{1^2 + 2^2} = \sqrt{5}$.
4. Unit direction of maximum increase: $\vec{u} = \langle 1, 2\rangle/\sqrt{5} = \langle 1/\sqrt{5}, 2/\sqrt{5}\rangle$.
5. Maximum rate of increase: $|\nabla f(2, 0)| = \sqrt{5}$.

**EVALUATE**: Since $f_y = 2 f_x$ at this point, the gradient is twice as steep in the $y$-direction as in the $x$-direction, so the steepest-ascent direction leans toward $+y$ — consistent with $\vec{u} = \langle 1, 2\rangle/\sqrt{5}$. The rate $\sqrt{5} \approx 2.24$ units of $f$ per unit distance is positive and finite, matching the expectation that $\nabla f \ne \vec{0}$ at $(2, 0)$ (a regular point). As a cross-check, the directional derivative along $\hat{\imath}$ is $\nabla f\cdot\hat{\imath} = 1 < \sqrt{5}$, confirming that $\hat{\imath}$ is not the steepest direction.
