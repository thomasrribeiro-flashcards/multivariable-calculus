+++
order = 6
tags = ["math", "multivariable-calculus", "partial-derivatives", "higher-order", "clairaut", "differentiability"]
+++

# Multivariable Calculus — Partial Derivatives

## 6.1 Motivation: Varying One Variable at a Time

Q: Why do we need a new kind of derivative for functions of several variables?
A: A function $f(x, y)$ changes as we move in many different directions, so a single "rate of change" is not well-defined. Partial derivatives pin down how $f$ changes when only one input varies and the others are held fixed. This reduces a hard multidimensional question to a familiar one-variable calculus problem. It is the first and simplest way to probe the local behavior of $f$.

Q: If we hold $y = b$ fixed in $f(x, y)$, what kind of object do we get?
A: We get a single-variable function $g(x) = f(x, b)$ whose graph is the trace of the surface $z = f(x, y)$ in the plane $y = b$. All standard single-variable calculus applies to $g$. The partial derivative with respect to $x$ is exactly $g'(x)$. This is the conceptual bridge from one-variable to multivariable calculus.

Q: Why is freezing all but one variable a natural first step rather than a special trick?
A: Because any notion of "rate of change" must specify a direction, and the simplest directions to choose are along the coordinate axes. Holding other variables fixed isolates the pure dependence on one input. Later tools (gradient, directional derivative, differentiability) are built from these axis-aligned rates. Understanding $f_x$ and $f_y$ first keeps the geometry simple.

C: Holding $y$ fixed and varying only $x$ reduces $f(x, y)$ to a [single-variable] function of $x$.

## 6.2 Definition of $f_x(a, b)$

Q: Before reading the formal definition, predict how $f_x(a, b)$ should be defined by analogy with the single-variable derivative.
A: One expects a limit of a difference quotient in which only $x$ changes while $y = b$ stays fixed. That is, $f_x(a, b)$ should be the ordinary derivative at $x = a$ of $g(x) = f(x, b)$. The $y$-coordinate is a spectator, not a variable to perturb. This intuition matches the real definition exactly.

C: The partial derivative with respect to $x$ at $(a, b)$ is defined as $f_x(a, b) = [\lim_{h \to 0} \frac{f(a+h, b) - f(a, b)}{h}]$, where $h$ is the increment in $x$ and $b$ is held fixed.

Q: In the definition $f_x(a, b) = \lim_{h \to 0}\frac{f(a+h, b) - f(a, b)}{h}$, why does only $x$ receive the increment $h$?
A: Because a partial derivative measures the rate of change in one coordinate direction only. The second slot must stay at $b$ for the quotient to represent motion along the line $y = b$. Letting $y$ vary too would mix two different rates and produce something else (a directional or total derivative). The variable $h$ is the signed displacement in $x$ and $b$ is frozen.

Q: When does $f_x(a, b)$ fail to exist?
A: When the one-variable limit above fails to exist: for example, if the trace $g(x) = f(x, b)$ has a corner, cusp, jump, or oscillatory non-limit at $x = a$. Existence of $f_x(a, b)$ is entirely a single-variable question about $g$ at $a$. Everything that can go wrong for ordinary derivatives can go wrong here.

## 6.3 Definition of $f_y(a, b)$

C: The partial derivative with respect to $y$ at $(a, b)$ is $f_y(a, b) = [\lim_{k \to 0} \frac{f(a, b+k) - f(a, b)}{k}]$, where $k$ is the increment in $y$ and $a$ is held fixed.

Q: Why must $f_x(a, b)$ and $f_y(a, b)$ be defined by separate limits rather than a single combined one?
A: They measure changes in two independent directions, and a single limit of $f(a+h, b+k)$ as $(h, k) \to (0, 0)$ depends on the path of approach. To get well-defined directional rates, we restrict to one coordinate axis at a time. The result is two scalar numbers, one per axis. These two numbers together are the first-order data of $f$ at $(a, b)$.

Q: If $f(x, y)$ depends only on $x$, what is $f_y(a, b)$ for every $(a, b)$, and why?
A: It is $0$, because $f(a, b+k) = f(a, b)$ for all $k$, so the difference quotient is identically zero. No change in $y$ produces any change in $f$. This is a sanity check: the partial $f_y$ detects genuine $y$-dependence.

## 6.4 Computing Partial Derivatives

Q: What is the practical rule for computing $f_x$ and $f_y$ without evaluating limits?
A: To compute $f_x$, treat $y$ as a constant and differentiate $f$ with respect to $x$ using all the usual one-variable rules (power, product, quotient, chain). For $f_y$, swap the roles: treat $x$ as a constant. This works because, pointwise, the partial derivative is literally the derivative of the frozen-$y$ (or frozen-$x$) trace. No new calculus rules are needed.

Q: When computing $f_x$ for $f(x, y) = x^2 y + \sin(xy)$, why does the term $\sin(xy)$ produce $y\cos(xy)$ rather than $\cos(xy)$?
A: Because with $y$ held constant, $\sin(xy)$ is a composition with inner function $u(x) = xy$, whose derivative with respect to $x$ is $y$. The chain rule then gives $\frac{d}{dx}\sin(xy) = \cos(xy) \cdot y$. Forgetting the factor of $y$ is the single most common error. Always ask "what multiplies $x$ inside?" and carry that factor out.

C: To compute $f_x$, treat every variable other than $x$ as a [constant], then differentiate using single-variable rules.

C: For $f(x, y) = x^2 y^3$, $f_x = [2x y^3]$ and $f_y = [3 x^2 y^2]$, where $y$ is held fixed for $f_x$ and $x$ is held fixed for $f_y$.

## 6.5 Notation

C: Common notations for the partial of $f$ with respect to $x$ include $f_x$, $[\partial f / \partial x]$, and $D_1 f$, all denoting the same function.

Q: What is the meaning of the "1" in the notation $D_1 f$?
A: It indicates differentiation with respect to the first argument (position slot) of $f$, independent of the name of the variable. Similarly $D_2 f$ means differentiation with respect to the second argument. This positional notation is useful when composing functions where variable names would be ambiguous. It avoids confusion like whether $\partial f / \partial x$ refers to the original $x$ or a substituted one.

Q: Why is $\partial$ used for partial derivatives instead of the ordinary $d$?
A: To signal that other variables are being held fixed, distinguishing a partial rate from an ordinary (total) derivative. The symbol $\partial$ is a stylized "d" reserved for this context. When $f$ is a function of one variable, $df/dx$ and $\partial f/\partial x$ coincide, but in multiple variables the distinction matters.

## 6.6 Geometric Interpretation

Q: What does $f_x(a, b)$ mean geometrically on the surface $z = f(x, y)$?
A: It is the slope of the trace curve obtained by intersecting the surface with the vertical plane $y = b$, measured at the point $(a, b, f(a, b))$. Equivalently, it is the slope of the tangent line to that trace in the direction of increasing $x$. The trace is a one-variable curve, and $f_x$ is its ordinary slope.

Q: In the same surface picture, what does $f_y(a, b)$ represent?
A: The slope of the trace obtained by intersecting the surface with the vertical plane $x = a$, at the point $(a, b, f(a, b))$, measured in the direction of increasing $y$. It is perpendicular in the $xy$-plane to the trace used for $f_x$. Together the two slopes determine the tangent plane at that point (when $f$ is differentiable).

C: Geometrically, $f_x(a, b)$ is the slope of the [trace] of $z = f(x, y)$ in the plane $y = b$, measured at $x = a$.

## 6.7 Higher-Order Partial Derivatives

Q: What does $f_{xx}$ mean, and how is it computed?
A: $f_{xx}$ is the partial derivative of $f_x$ with respect to $x$ again, treating $y$ as constant both times. It measures the concavity of the trace $g(x) = f(x, b)$ at each $(a, b)$. Computationally, differentiate twice with respect to $x$, treating $y$ as a constant throughout. Analogously, $f_{yy} = \partial^2 f / \partial y^2$ uses $y$ twice.

C: The second partial $f_{yy}$ equals $[\partial^2 f / \partial y^2]$, obtained by differentiating $f$ twice with respect to $y$ while holding $x$ fixed.

Q: Why do second-order partials carry more information than first-order partials?
A: First partials describe rate of change, but second partials describe how that rate itself changes — curvature along each coordinate direction. They appear in optimization (second-derivative test), stability analysis, and every major PDE. They are the building blocks of the Hessian matrix, which encodes local quadratic behavior.

## 6.8 Mixed Partial Derivatives

C: The mixed partial $f_{xy}$ is defined as $[\partial/\partial y (\partial f/\partial x)]$, meaning first differentiate with respect to $x$, then with respect to $y$.

Q: What is the difference in reading order between $f_{xy}$ and $\partial^2 f / \partial x\, \partial y$?
A: In subscript notation $f_{xy}$, one differentiates left to right: first $x$, then $y$. In Leibniz notation $\partial^2 f / \partial x\, \partial y$, one reads from the denominator right to left: first the rightmost variable ($y$), then the next ($x$). Both conventions describe the same operation when Clairaut's theorem applies, but the ordering convention can trip students up. Always check which notation the book uses.

Q: Intuitively, what does $f_{xy}$ measure?
A: It measures how the $x$-slope of $f$ changes as $y$ varies. Equivalently, it measures the coupling between the two variables: if $f_{xy} \ne 0$, changing $y$ alters the rate at which $f$ responds to $x$. For additively separable $f(x, y) = g(x) + h(y)$, $f_{xy} \equiv 0$.

## 6.9 Clairaut's Theorem

Q: What does Clairaut's theorem state, and what is its hypothesis?
A: If $f_{xy}$ and $f_{yx}$ both exist and are continuous on an open region containing $(a, b)$, then $f_{xy}(a, b) = f_{yx}(a, b)$. The hypothesis is the joint continuity of both mixed partials near the point. Without continuity, the two mixed partials can disagree, even when both exist.

Q: Why is Clairaut's theorem so useful in practice?
A: It lets us differentiate in either order when computing mixed partials and exchange integration/differentiation orders in applications. Most functions encountered in practice (polynomials, trig, exponentials, and their compositions) have continuous partials of all orders, so the hypothesis is automatic. This is why students rarely see counterexamples outside textbooks.

C: Clairaut's theorem: if both mixed partials are continuous near $(a, b)$, then $f_{xy}(a, b) = [f_{yx}(a, b)]$.

Q: Give the idea behind a counterexample where $f_{xy}(0,0) \ne f_{yx}(0,0)$.
A: Functions like $f(x, y) = xy(x^2 - y^2)/(x^2 + y^2)$ (with $f(0,0) = 0$) have all partials existing everywhere, but $f_{xy}$ and $f_{yx}$ are discontinuous at the origin and evaluate to $-1$ and $+1$ there. The pathology lives exactly at the one point where continuity fails. Away from the origin, both mixed partials agree as expected.

## 6.10 Differentiability in Several Variables

Q: What is the definition of differentiability for $f: \mathbb{R}^2 \to \mathbb{R}$ at $(a, b)$?
A: $f$ is differentiable at $(a, b)$ if there exist numbers $A, B$ such that $f(a+h, b+k) - f(a, b) - (Ah + Bk) = o(\sqrt{h^2 + k^2})$ as $(h, k) \to (0, 0)$. That is, the linear map $(h, k) \mapsto Ah + Bk$ approximates the increment $f(a+h, b+k) - f(a, b)$ with error that vanishes faster than the distance $\sqrt{h^2+k^2}$. When this holds, $A = f_x(a, b)$ and $B = f_y(a, b)$. This is the genuine multivariable analogue of one-variable differentiability.

Q: Why is "differentiable" strictly stronger than "both partials exist" in several variables?
A: Existence of $f_x$ and $f_y$ only controls behavior along the two coordinate axes. Differentiability demands that the linear approximation $Ah + Bk$ works along every approach direction, with the error shrinking faster than distance. A function can pass the weak axis-only tests and still misbehave diagonally, so partials existing is not enough.

C: Differentiability of $f$ at $(a, b)$ requires that the increment $f(a+h, b+k) - f(a, b) - (f_x h + f_y k)$ shrinks to zero faster than $[\sqrt{h^2 + k^2}]$ as $(h, k) \to (0, 0)$.

## 6.11 Partials Without Differentiability

Q: Can a function have $f_x$ and $f_y$ everywhere yet fail to be continuous at some point?
A: Yes. The standard example is $f(x, y) = xy/(x^2 + y^2)$ with $f(0, 0) = 0$. Along either axis $f$ is identically zero, so $f_x(0, 0) = f_y(0, 0) = 0$ exist. But along the line $y = x$, $f = 1/2$, so $f$ is not continuous at the origin. Hence the function is not even continuous, let alone differentiable.

Q: Why does this example not contradict any theorem?
A: Because partials capture only axis-aligned behavior, whereas continuity (and differentiability) require control along every approach path. No theorem promises continuity from partial-derivative existence alone. The example precisely exhibits pathological diagonal behavior invisible to axis-aligned tests.

C: In several variables, existence of $f_x$ and $f_y$ at a point does not imply [continuity] of $f$ at that point.

## 6.12 Continuous Partials Imply Differentiability

Q: What is the main sufficient condition for differentiability that is easy to check?
A: If $f_x$ and $f_y$ exist on an open set containing $(a, b)$ and are continuous at $(a, b)$, then $f$ is differentiable at $(a, b)$. This is the workhorse theorem: most explicit functions have continuous partials, so differentiability is automatic for them. The proof uses the mean value theorem coordinate by coordinate to bound the approximation error.

Q: Why is this theorem practically more useful than the raw definition of differentiability?
A: Checking the definition requires proving an $o(\sqrt{h^2+k^2})$ estimate along every direction, which is tedious. Checking continuity of two partials is a routine calculation. Hence in practice one computes $f_x, f_y$, confirms they are continuous, and concludes differentiability immediately.

C: If $f_x$ and $f_y$ are both [continuous] on an open set around $(a, b)$, then $f$ is differentiable at $(a, b)$.

## 6.13 The Total Differential

Q: What is the total differential of a differentiable function $f(x, y)$?
A: It is the expression $df = f_x(x, y)\,dx + f_y(x, y)\,dy$, a linear function of the increments $dx$ and $dy$. Here $dx$ and $dy$ are small displacements in $x$ and $y$, and $df$ is the corresponding linear approximation of the change in $f$. It generalizes the one-variable $df = f'(x)\,dx$ by summing contributions from each input.

C: The total differential of $f(x, y)$ is $df = [f_x \, dx + f_y \, dy]$, where $dx$ and $dy$ are the increments in $x$ and $y$.

Q: Why is the total differential the "right" first-order object for $f(x, y)$, rather than $f_x$ or $f_y$ alone?
A: Because $df$ encodes the combined first-order response of $f$ to arbitrary small motion in the $(x, y)$-plane, not just axis-aligned motion. The coefficients $f_x, f_y$ form the row of the Jacobian matrix, and $df$ is this matrix acting on the increment vector. It is coordinate-independent in spirit and sets up the chain rule and gradient cleanly.

## 6.14 Linear Approximation

Q: How is the total differential used for linear approximation near $(a, b)$?
A: For $(x, y)$ near $(a, b)$, $f(x, y) \approx f(a, b) + f_x(a, b)(x - a) + f_y(a, b)(y - b)$. The right-hand side is the equation of the tangent plane to $z = f(x, y)$ at $(a, b)$. The approximation error is $o(\sqrt{(x-a)^2 + (y-b)^2})$ when $f$ is differentiable. This is the direct multivariable analogue of $f(x) \approx f(a) + f'(a)(x - a)$.

Q: What does the tangent-plane approximation fail to do if $f$ is not differentiable at $(a, b)$?
A: Even if $f_x(a, b)$ and $f_y(a, b)$ exist, the expression $f(a, b) + f_x(x-a) + f_y(y-b)$ can miss the true values of $f$ by more than $o(\sqrt{(x-a)^2+(y-b)^2})$ along some approach direction. The "tangent plane" may not actually be tangent to the surface in any geometric sense. Differentiability is exactly what makes the tangent plane valid.

C: For a differentiable $f$, the [tangent plane] approximation near $(a, b)$ is $f(x, y) \approx f(a, b) + f_x(a, b)(x - a) + f_y(a, b)(y - b)$.

## 6.15 Laplace's Equation and Harmonic Functions

C: Laplace's equation in two variables is $[f_{xx} + f_{yy}] = 0$, where $f_{xx}$ and $f_{yy}$ are the unmixed second partials of $f$.

Q: What is a harmonic function, and where do they show up?
A: A function $f(x, y)$ is harmonic on a region if it has continuous second partials there and satisfies Laplace's equation $f_{xx} + f_{yy} = 0$. Harmonic functions model steady-state heat distributions, electrostatic potentials in charge-free regions, and incompressible irrotational fluid flow. They also coincide with the real and imaginary parts of holomorphic functions from complex analysis.

Q: Why is Laplace's equation a natural equation to study?
A: It describes equilibrium: the value at each point equals the average of its neighbors (mean value property). This captures the absence of local sources, sinks, or curvature bias. It is the simplest linear second-order PDE with no time dependence and is the prototype of all "elliptic" PDEs.

## 6.16 Wave and Heat Equations

Q: What is the one-dimensional heat equation, and what does it describe?
A: It is $u_t = \alpha u_{xx}$, where $u(x, t)$ is temperature at position $x$ and time $t$, and $\alpha > 0$ is the thermal diffusivity. It says temperature at a point rises or falls in proportion to the spatial concavity of the temperature profile. Hot bumps flatten and cold dips fill in over time. It is the prototype of parabolic PDEs.

Q: What is the one-dimensional wave equation, and what does it describe?
A: It is $u_{tt} = c^2 u_{xx}$, where $u(x, t)$ is the displacement of a vibrating string at position $x$ and time $t$, and $c > 0$ is the wave speed. Acceleration in time equals curvature in space times $c^2$. Solutions are superpositions of left- and right-moving waves. It is the prototype of hyperbolic PDEs.

C: The one-dimensional heat equation is $u_t = [\alpha u_{xx}]$, where $u(x, t)$ is temperature and $\alpha > 0$ is the thermal diffusivity.

C: The one-dimensional wave equation is $u_{tt} = [c^2 u_{xx}]$, where $u(x, t)$ is displacement and $c > 0$ is the wave speed.

Q: Why are heat, wave, and Laplace equations all built from second partials?
A: Because second partials encode curvature, and most physical laws (diffusion, elasticity, equilibrium) relate local curvature to forces, fluxes, or time changes. First partials carry too little information — they miss the notion of "how bent" a field is. Second-order PDEs are thus the natural language of continuum physics.

## 6.17 Computing All Four Second Partials

P: Compute all four second partial derivatives of $f(x, y) = x^3 y - 2 x y^2 + \sin(x y)$ and verify Clairaut's theorem.

S:
**IDENTIFY**: Higher-order partial derivative computation on a $C^\infty$ function; expect $f_{xy} = f_{yx}$ by Clairaut because all partials will be continuous everywhere.

**PLAN**:
- Compute $f_x$ by treating $y$ as constant.
- Compute $f_y$ by treating $x$ as constant.
- Differentiate $f_x$ in $x$ to get $f_{xx}$, in $y$ to get $f_{xy}$.
- Differentiate $f_y$ in $y$ to get $f_{yy}$, in $x$ to get $f_{yx}$.
- Check $f_{xy} = f_{yx}$ as a sanity check.

**EXECUTE**:
1. First partials:
   - $f_x = 3 x^2 y - 2 y^2 + y \cos(xy)$ (chain rule: derivative of $\sin(xy)$ w.r.t. $x$ is $y\cos(xy)$).
   - $f_y = x^3 - 4 x y + x \cos(xy)$.
2. $f_{xx} = \partial f_x / \partial x = 6 x y + 0 + y \cdot (-\sin(xy)) \cdot y = 6 x y - y^2 \sin(xy)$.
3. $f_{yy} = \partial f_y / \partial y = 0 - 4 x + x \cdot (-\sin(xy)) \cdot x = -4 x - x^2 \sin(xy)$.
4. $f_{xy} = \partial f_x / \partial y = 3 x^2 - 4 y + \cos(xy) + y \cdot (-\sin(xy)) \cdot x = 3 x^2 - 4 y + \cos(xy) - x y \sin(xy)$.
5. $f_{yx} = \partial f_y / \partial x = 3 x^2 - 4 y + \cos(xy) + x \cdot (-\sin(xy)) \cdot y = 3 x^2 - 4 y + \cos(xy) - x y \sin(xy)$.

**EVALUATE**:
- $f_{xy} = f_{yx} = 3 x^2 - 4 y + \cos(xy) - x y \sin(xy)$, confirming Clairaut's theorem, as expected for this smooth function.
- Units and degrees match: each term in $f_{xx}, f_{yy}, f_{xy}$ is one differentiation lower in appropriate variable than $f$.
- Cross-check at $(0, 0)$: $f_{xy}(0, 0) = 0 - 0 + 1 - 0 = 1 = f_{yx}(0, 0)$.

## 6.18 Verifying a Harmonic Function

P: Verify that $f(x, y) = \ln(x^2 + y^2)$ is harmonic on $\mathbb{R}^2 \setminus \{(0, 0)\}$.

S:
**IDENTIFY**: We must show $f$ satisfies Laplace's equation $f_{xx} + f_{yy} = 0$ wherever it is defined, namely for $(x, y) \ne (0, 0)$.

**PLAN**:
- Let $r^2 = x^2 + y^2$, so $f = \ln(r^2)$.
- Compute $f_x$ and $f_y$ using the chain rule.
- Differentiate again using the quotient rule to get $f_{xx}$ and $f_{yy}$.
- Add them and show the sum is $0$.

**EXECUTE**:
1. First partials (chain rule: $\partial_x \ln(x^2 + y^2) = (2x)/(x^2+y^2)$):
   - $f_x = \frac{2x}{x^2 + y^2}$.
   - $f_y = \frac{2y}{x^2 + y^2}$.
2. Second partial $f_{xx}$ via the quotient rule $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$ with $u = 2x$, $v = x^2+y^2$:
   - $u' = 2$, $v' = 2x$ (w.r.t. $x$, with $y$ fixed).
   - $f_{xx} = \frac{2(x^2 + y^2) - 2x \cdot 2x}{(x^2 + y^2)^2} = \frac{2 y^2 - 2 x^2}{(x^2 + y^2)^2}$.
3. By the symmetric calculation (swap $x \leftrightarrow y$):
   - $f_{yy} = \frac{2 x^2 - 2 y^2}{(x^2 + y^2)^2}$.
4. Sum: $f_{xx} + f_{yy} = \frac{(2y^2 - 2x^2) + (2x^2 - 2y^2)}{(x^2 + y^2)^2} = \frac{0}{(x^2+y^2)^2} = 0$.

**EVALUATE**:
- The sum vanishes identically wherever the expression is defined, i.e., for $(x, y) \ne (0, 0)$.
- At the origin, $f$ itself is undefined, so the equation is not required to hold there.
- This is a classic example: $\ln(x^2 + y^2) = 2 \ln r$ is, up to a constant, the fundamental solution of the 2D Laplacian, matching the known result that $\ln r$ is harmonic away from the origin.
