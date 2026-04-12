+++
order = 5
tags = ["math", "multivariable-calculus", "functions-several-variables", "limits", "continuity", "level-curves"]
+++

# Multivariable Calculus — Functions of Several Variables, Limits, and Continuity

## 5.1 Functions of Several Variables

Q: Why do we generalize from single-variable functions $f:\mathbb{R}\to\mathbb{R}$ to functions of several variables $f:\mathbb{R}^n\to\mathbb{R}$?
A: Most real quantities depend on more than one input. Temperature in a room depends on position $(x, y, z)$; profit depends on price and quantity; a height on a map depends on latitude and longitude. A single-variable model cannot capture this coupling, so we need functions whose inputs are points of $\mathbb{R}^n$ and whose output is a real number.

C: A scalar-valued function of $n$ variables is a map [$f:\mathbb{R}^n\to\mathbb{R}$] that assigns each input point $(x_1,\ldots,x_n)$ a single real number $f(x_1,\ldots,x_n)$.

C: For a function $f:\mathbb{R}^n\to\mathbb{R}$, the integer $n$ is called the [number of independent variables] (or the dimension of the input space).

Q: How does a function of two variables $f(x, y)$ differ structurally from a function of one variable $f(x)$?
A: The input is now an ordered pair $(x, y)\in\mathbb{R}^2$ rather than a single number, so the "graph" lives in $\mathbb{R}^3$ rather than $\mathbb{R}^2$. Concepts like limit, continuity, and derivative must be rebuilt because we can approach an input point from infinitely many directions, not just from the left or right.

C: For a function $f:\mathbb{R}^n\to\mathbb{R}^m$ with $m > 1$, the output is a vector and the function is called [vector-valued] (as opposed to scalar-valued when $m = 1$).

## 5.2 Domain and Range

Q: What is the domain of a multivariable function $f(x, y)$, and why does it matter?
A: The domain is the set of all input points $(x, y)\in\mathbb{R}^2$ for which the defining expression yields a real number. It matters because it determines where limits and continuity questions can even be asked; evaluating $f$ outside the domain is undefined.

C: The [domain] of $f(x, y)$ is the largest subset of $\mathbb{R}^2$ on which the formula for $f$ produces a real value, and the [range] is the set of all output values $f(x, y)$ as $(x, y)$ runs over the domain.

Q: Why is the domain of $f(x, y) = \sqrt{1 - x^2 - y^2}$ the closed unit disk?
A: The square root requires $1 - x^2 - y^2 \ge 0$, i.e. $x^2 + y^2 \le 1$, where $x$ and $y$ are the coordinates of the input point. This is the closed disk of radius 1 centered at the origin, including the boundary circle.

Q: Why is the domain of $f(x, y) = \ln(x - y)$ an open half-plane?
A: The logarithm requires a strictly positive argument, so $x - y > 0$, which is the open half-plane above no line — specifically, all points below the line $y = x$. The boundary line $y = x$ is excluded because $\ln(0)$ is undefined.

P: Find the domain and range of $f(x, y) = \sqrt{4 - x^2 - y^2}$, where $x$ and $y$ are the two input coordinates.

S:
**IDENTIFY**: Domain/range problem for a square-root expression in two variables.

**PLAN**:
- Domain: force the radicand to be nonnegative.
- Range: analyze the values the square root can take over the domain.

**EXECUTE**:
1. Require $4 - x^2 - y^2 \ge 0 \Rightarrow x^2 + y^2 \le 4$ (closed disk of radius 2).
2. At center $(0,0)$: $f = 2$ (maximum, since radicand is maximized).
3. On boundary circle $x^2 + y^2 = 4$: $f = 0$ (minimum).
4. All intermediate values occur, so range is $[0, 2]$.

**EVALUATE**: Domain $= \{(x,y) : x^2 + y^2 \le 4\}$, range $= [0, 2]$. Sanity check: $f$ is continuous on a compact set, so it must attain its extremes — consistent with a closed interval range.

## 5.3 Graph as a Surface in $\mathbb{R}^3$

C: The graph of $z = f(x, y)$ is the set of points [$(x, y, f(x, y))$] in $\mathbb{R}^3$, where $(x, y)$ runs over the domain of $f$; this graph is a surface sitting above (or below) the $xy$-plane.

Q: Why does the graph of $z = f(x, y)$ live in $\mathbb{R}^3$ rather than $\mathbb{R}^2$?
A: Two coordinates encode the input and one coordinate encodes the output, so each input-output pair is a triple $(x, y, z)$ with $z = f(x, y)$. Plotting all such triples fills out a 2D surface embedded in 3D space — analogous to how a 1D curve $y = f(x)$ sits in 2D space.

Q: Why can we not usefully graph $f(x, y, z)$ (three inputs) as a surface?
A: Its graph would require four dimensions: three for the input and one for the output. We cannot visualize $\mathbb{R}^4$ directly, so for three-variable functions we switch to level surfaces in $\mathbb{R}^3$ instead of graphing.

Q: What surface is the graph of $f(x, y) = x^2 + y^2$, and why?
A: A circular paraboloid opening upward along the positive $z$-axis. For any fixed $z = c > 0$, the cross section $x^2 + y^2 = c$ is a circle of radius $\sqrt{c}$, and the cross sections grow with $z$ — the signature of a paraboloid of revolution.

## 5.4 Level Curves and Contour Maps

C: A [level curve] of $f(x, y)$ at height $c$ is the set $\{(x, y) : f(x, y) = c\}$ in the $xy$-plane, where $c$ is a fixed real constant called the level.

Q: Why are level curves useful for visualizing $f(x, y)$?
A: They reduce a 3D surface to a 2D picture by "slicing" the graph $z = f(x, y)$ with horizontal planes $z = c$ and projecting each slice down to the $xy$-plane. A collection of level curves at evenly spaced $c$ values (a contour map) conveys steepness and shape without needing 3D rendering.

C: A [contour map] is a collection of level curves of $f(x, y)$ drawn in the $xy$-plane at evenly spaced values of $c$, commonly used in topographic maps where $f$ is elevation.

Q: Why do closely spaced contour lines indicate a steep region of the graph?
A: Closely spaced contours mean $f$ changes by a fixed step $\Delta c$ over a small horizontal distance, so the ratio $\Delta c / \text{distance}$ is large — which is exactly what steepness measures. Widely spaced contours indicate gentle slopes.

Q: What are the level curves of $f(x, y) = x^2 + y^2$?
A: Circles $x^2 + y^2 = c$ centered at the origin with radius $\sqrt{c}$, defined for $c \ge 0$. At $c = 0$ the "curve" degenerates to the single point $(0, 0)$; for $c < 0$ the level set is empty because the function is nonnegative.

Q: Why can level curves for different values of $c$ never intersect?
A: If a point $(x_0, y_0)$ lay on two different level curves $f = c_1$ and $f = c_2$ with $c_1 \ne c_2$, then $f(x_0, y_0)$ would equal both $c_1$ and $c_2$ simultaneously — impossible because $f$ is single-valued.

## 5.5 Level Surfaces

C: A [level surface] of $f(x, y, z)$ at level $c$ is the set $\{(x, y, z) : f(x, y, z) = c\}\subset\mathbb{R}^3$, where $c$ is a fixed real constant.

Q: Why do we use level surfaces instead of graphs for functions $f(x, y, z)$ of three variables?
A: The graph would require $\mathbb{R}^4$, which we cannot visualize. Level surfaces trade the output dimension for a family of 3D surfaces in the input space, letting us see how $f$ varies in space by looking at how the surfaces nest.

Q: What are the level surfaces of $f(x, y, z) = x^2 + y^2 + z^2$?
A: Concentric spheres $x^2 + y^2 + z^2 = c$ of radius $\sqrt{c}$ centered at the origin, defined for $c \ge 0$. At $c = 0$ the surface degenerates to the single point at the origin; at $c < 0$ the set is empty.

## 5.6 Why Multivariable Limits Are Harder

Q: Why is taking a limit in two variables fundamentally harder than in one variable?
A: In one variable, $x$ can only approach $a$ from the left or the right, giving two one-sided limits to match. In two variables, $(x, y)$ can approach $(a, b)$ along infinitely many paths — straight lines of every slope, parabolas, spirals, and more — and the limit exists only if every such path gives the same value.

C: For $\lim_{(x,y)\to(a,b)} f(x, y) = L$ to exist, $f(x, y)$ must approach the same value $L$ along [every possible path] through $(a, b)$ in the domain.

Q: Why does the existence of the limit along 100 straight lines not guarantee the limit exists?
A: Limits can fail along a curved path (like $y = x^2$) even when every straight line gives the same value. Because infinitely many path shapes are possible, checking finitely many paths can only disprove a limit, never prove one.

## 5.7 Formal $\epsilon$–$\delta$ Definition

C: $\lim_{(x,y)\to(a,b)} f(x, y) = L$ means: for every $\epsilon > 0$ there exists [$\delta > 0$] such that $0 < \sqrt{(x-a)^2 + (y-b)^2} < \delta$ implies $|f(x, y) - L| < \epsilon$, where $\epsilon$ is the target output tolerance and $\delta$ is the input-neighborhood radius.

Q: What geometric picture corresponds to the $\epsilon$–$\delta$ definition of a multivariable limit?
A: Draw a punctured open disk of radius $\delta$ around $(a, b)$ in the $xy$-plane and a horizontal band of half-width $\epsilon$ around $z = L$ in the output. The definition says: for any output band you choose, there is some input disk small enough that the graph above that disk stays inside the band.

Q: Why is the input neighborhood in a 2-variable limit a disk rather than an interval?
A: "Closeness" between input points $(x, y)$ and $(a, b)$ is measured by Euclidean distance $\sqrt{(x-a)^2 + (y-b)^2}$, so the set of points within distance $\delta$ is an open disk, not an interval. In $\mathbb{R}^n$ it generalizes to an open ball.

C: In the $\epsilon$–$\delta$ definition of a multivariable limit, the punctured neighborhood is a [disk] (or ball in $\mathbb{R}^n$) of radius $\delta$ centered at $(a,b)$, excluding the center point itself.

## 5.8 Limit Along a Path

Q: What does it mean to take a limit "along a path" $y = g(x)$ through $(a, b)$?
A: We restrict $f(x, y)$ to the curve $y = g(x)$ (assuming $g(a) = b$) and compute the one-variable limit $\lim_{x\to a} f(x, g(x))$. If this differs from the candidate limit $L$, the full multivariable limit cannot equal $L$.

C: If $\lim_{(x,y)\to(a,b)} f(x, y)$ exists and equals $L$, then along [every path] through $(a, b)$ in the domain, the one-variable limit also equals $L$.

Q: Why is the path method a one-sided tool — good for disproving limits but weak for proving them?
A: To disprove, you just need two paths giving different values, which is a finite check. To prove, you would need every path to give the same value, but there are infinitely many possible paths — no finite inspection suffices. Proofs require $\epsilon$–$\delta$, polar coordinates, or the squeeze theorem.

## 5.9 Two Paths, Different Limits

C: If two paths through $(a, b)$ yield [different limit values] for $f$, then $\lim_{(x,y)\to(a,b)} f(x, y)$ does not exist.

Q: Why does finding two paths with different limits conclusively disprove the multivariable limit?
A: The hypothesis of a limit $L$ forces agreement along every path. A single disagreement between two paths directly contradicts this, so no single value $L$ can satisfy the definition. This is a logical $\textit{reductio}$: one counterexample refutes universal agreement.

## 5.10 Path-Test Substitutions: $y = mx$ and $y = kx^2$

Q: Why is substituting $y = mx$ a useful first test for non-existence of a limit at the origin?
A: It lets us check all straight lines through $(0, 0)$ at once. If the resulting one-variable limit in $x$ depends on the slope $m$, different lines give different values and the multivariable limit fails to exist.

Q: Why do we sometimes need to try $y = kx^2$ after lines fail to reveal path dependence?
A: Some functions give the same value along every line through the origin but different values along parabolic paths, because the numerator and denominator scale differently on parabolas than on lines. Testing $y = kx^2$ probes this and can expose a hidden path dependence that lines miss.

C: Substituting $y = mx$ into $f(x, y)$ and taking $\lim_{x\to 0}$ tests path dependence along [straight lines through the origin], where $m$ is the slope parameter.

C: Substituting $y = kx^2$ into $f(x, y)$ and taking $\lim_{x\to 0}$ tests path dependence along [parabolas tangent to the $x$-axis at the origin], where $k$ is the parabola's curvature parameter.

## 5.11 Polar Coordinates for Limits at the Origin

Q: Why is switching to polar coordinates $(r, \theta)$ helpful for limits at the origin?
A: Polar coordinates replace the two-variable approach $(x, y)\to(0,0)$ with the single constraint $r\to 0^+$, where $r = \sqrt{x^2 + y^2}$ is the distance to the origin. If after substitution the expression has the form $r^k \cdot g(\theta)$ with $k > 0$ and $g$ bounded, we conclude the limit is 0 uniformly in $\theta$.

C: In polar coordinates, $x = [r\cos\theta]$ and $y = [r\sin\theta]$, where $r \ge 0$ is the distance from the origin and $\theta$ is the angle measured from the positive $x$-axis.

C: If after polar substitution $|f(x, y)| \le r^k \cdot M$ for some $k > 0$ and constant $M$ independent of $\theta$, then $\lim_{(x,y)\to(0,0)} f(x, y) = [0]$.

Q: Why does the polar method fail when the angular factor $g(\theta)$ is not bounded or when the $r$-dependence disappears?
A: If $g(\theta)$ blows up for some $\theta$, or if all $r$ factors cancel and the expression reduces to a function of $\theta$ alone, then the value depends on the angle of approach. Different $\theta$ values give different limits, so the limit does not exist.

## 5.12 Squeeze Theorem in Multiple Variables

C: Squeeze theorem (2 variables): if $g(x, y) \le f(x, y) \le h(x, y)$ near $(a, b)$ and $\lim_{(x,y)\to(a,b)} g = \lim_{(x,y)\to(a,b)} h = L$, then $\lim_{(x,y)\to(a,b)} f = [L]$.

Q: Why is the squeeze theorem especially useful for expressions with bounded trig or oscillating factors?
A: Terms like $\sin(1/(x^2+y^2))$ oscillate and have no limit on their own, but they are bounded by $\pm 1$. Multiplying by something that goes to 0 gives a product squeezed between two sequences both tending to 0, forcing the limit to be 0 even though the oscillating factor misbehaves.

Q: How would you use the squeeze theorem on $f(x, y) = (x^2 + y^2)\sin(1/(x^2+y^2))$ as $(x,y)\to(0,0)$, where $x$ and $y$ are the input coordinates?
A: Since $|\sin(\cdot)|\le 1$, we have $0 \le |f(x,y)| \le x^2 + y^2$. Both $0$ and $x^2 + y^2$ tend to 0 as $(x,y)\to(0,0)$, so by the squeeze theorem $f\to 0$.

## 5.13 Continuity at a Point

C: $f(x, y)$ is continuous at $(a, b)$ iff $(a,b)$ is in the domain and $\lim_{(x,y)\to(a,b)} f(x, y) = [f(a, b)]$.

Q: Why does continuity at a point require three separate conditions?
A: We need (1) $f(a, b)$ to be defined — no continuity talk if the function is undefined there; (2) the limit $\lim_{(x,y)\to(a,b)} f$ to exist — so approach values agree; (3) the limit to equal the function value — so the point is not "jumped over." Failure of any one breaks continuity.

Q: Why is continuity the exact property that lets us evaluate limits by direct substitution?
A: Continuity at $(a, b)$ says the limit equals $f(a, b)$ by definition. So whenever we already know a function is continuous at a point, evaluating the limit reduces to plugging in coordinates — no path analysis needed.

## 5.14 Continuity of Common Building Blocks

C: [Polynomials] in $x$ and $y$ are continuous on all of $\mathbb{R}^2$, because they are built from continuous operations (sums, products) on the continuous coordinate functions $x$ and $y$.

C: A [rational function] $p(x,y)/q(x,y)$ (a quotient of polynomials) is continuous everywhere its denominator $q(x,y)$ is nonzero.

C: The elementary transcendental functions $\sin$, $\cos$, $e^x$, and $\ln$ (on their natural domains) are [continuous], so compositions like $\sin(xy)$ or $e^{x^2+y^2}$ inherit continuity.

Q: Why is $f(x, y) = \frac{1}{x - y}$ continuous on its domain even though it "blows up" somewhere?
A: It is a rational function, continuous wherever the denominator is nonzero. The line $y = x$ is not in the domain, so the blow-up is not a discontinuity in the domain — it is simply outside it. Continuity is only judged on domain points.

## 5.15 Composition Preserves Continuity

C: If $g:\mathbb{R}^n\to\mathbb{R}$ is continuous at $\mathbf{p}$ and $h:\mathbb{R}\to\mathbb{R}$ is continuous at $g(\mathbf{p})$, then [$h\circ g$] is continuous at $\mathbf{p}$.

Q: Why does composition of continuous functions produce a continuous function?
A: Continuity transmits tolerances: a small change in the inner function's output follows from a small change in its input, and a small change in the outer function's output follows from a small change in its input. Chaining these gives a small overall output change from a small overall input change — the $\epsilon$-$\delta$ statement of continuity.

Q: Why is $f(x, y) = \cos(x^2 + y^2)$ continuous everywhere on $\mathbb{R}^2$?
A: The inner function $g(x, y) = x^2 + y^2$ is a polynomial, hence continuous on $\mathbb{R}^2$. The outer function $\cos$ is continuous on all of $\mathbb{R}$. Their composition $\cos(x^2 + y^2)$ is therefore continuous everywhere.

## 5.16 Removable vs Non-removable Discontinuities

C: A discontinuity at $(a, b)$ is [removable] if $\lim_{(x,y)\to(a,b)} f(x, y)$ exists but does not equal $f(a, b)$ (or $f$ is undefined there); redefining $f(a, b)$ to equal the limit fixes continuity.

C: A discontinuity at $(a, b)$ is [non-removable] if $\lim_{(x,y)\to(a,b)} f(x, y)$ does not exist, typically because different paths give different values.

Q: Why can a path-dependent discontinuity never be "removed" by redefining $f$ at the point?
A: Removing a discontinuity requires a single well-defined limit to plug in. If the limit does not exist because paths disagree, no single value for $f(a, b)$ can make every approach agree — the mismatch is structural, not a hole in the domain.

Q: Why is $f(x, y) = \frac{\sin(x^2+y^2)}{x^2+y^2}$ (undefined at origin) only removably discontinuous there, where $x$ and $y$ are the input coordinates?
A: Using the substitution $u = x^2 + y^2$, as $(x,y)\to(0,0)$ we have $u\to 0$, and $\sin(u)/u \to 1$ along every path because this is a standard one-variable limit. Defining $f(0,0) = 1$ makes $f$ continuous at the origin.

## 5.17 Disproving a Limit by Two Paths

P: Show that $\lim_{(x,y)\to(0,0)} \dfrac{xy}{x^2 + y^2}$ does not exist by testing $y = 0$ and $y = x$, where $x$ and $y$ are the input coordinates.

S:
**IDENTIFY**: Non-existence-of-limit problem for a homogeneous rational function at the origin. Strategy: produce two paths with different limits.

**PLAN**:
- Path 1: $y = 0$ (the $x$-axis).
- Path 2: $y = x$ (the diagonal line).
- Compute the one-variable limit along each; if values differ, the limit does not exist.

**EXECUTE**:
1. Along $y = 0$: $f(x, 0) = \dfrac{x\cdot 0}{x^2 + 0^2} = \dfrac{0}{x^2} = 0$ for $x\ne 0$, so $\lim_{x\to 0} f(x, 0) = 0$.
2. Along $y = x$: $f(x, x) = \dfrac{x\cdot x}{x^2 + x^2} = \dfrac{x^2}{2x^2} = \dfrac{1}{2}$ for $x\ne 0$, so $\lim_{x\to 0} f(x, x) = \dfrac{1}{2}$.
3. The two path-limits disagree ($0\ne 1/2$).

**EVALUATE**: By the two-path criterion, $\lim_{(x,y)\to(0,0)} \dfrac{xy}{x^2+y^2}$ does not exist. Sanity check: the function is homogeneous of degree 0 — on any line $y = mx$ it simplifies to a constant $\frac{m}{1+m^2}$ depending on $m$, which confirms path-dependence on all lines, not just two.

## 5.18 Evaluating a Limit via Polar Coordinates

P: Use polar coordinates to evaluate $\lim_{(x,y)\to(0,0)} \dfrac{x^2 y}{x^2 + y^2}$, where $x$ and $y$ are the input coordinates.

S:
**IDENTIFY**: Candidate-limit problem at the origin. Numerator has degree 3, denominator has degree 2; degree of numerator exceeds denominator, so polar coordinates should expose an $r$-factor that forces the limit to 0.

**PLAN**:
- Substitute $x = r\cos\theta$, $y = r\sin\theta$, where $r = \sqrt{x^2+y^2}\ge 0$ and $\theta\in[0,2\pi)$.
- Simplify, bound the angular factor, and take $r\to 0^+$.

**EXECUTE**:
1. Numerator: $x^2 y = (r\cos\theta)^2(r\sin\theta) = r^3 \cos^2\theta \sin\theta$.
2. Denominator: $x^2 + y^2 = r^2(\cos^2\theta + \sin^2\theta) = r^2$.
3. Quotient: $\dfrac{x^2 y}{x^2 + y^2} = \dfrac{r^3 \cos^2\theta \sin\theta}{r^2} = r\cos^2\theta\sin\theta$.
4. Bound: $|r\cos^2\theta\sin\theta| \le r\cdot 1 \cdot 1 = r$, since $|\cos\theta|, |\sin\theta|\le 1$.
5. As $(x,y)\to(0,0)$, $r\to 0^+$, so by squeeze $r\cos^2\theta\sin\theta\to 0$.

**EVALUATE**: $\lim_{(x,y)\to(0,0)} \dfrac{x^2 y}{x^2 + y^2} = 0$. Sanity check: along $y = mx$, the function equals $\dfrac{m x^3}{(1+m^2)x^2} = \dfrac{m x}{1+m^2}\to 0$ for every $m$ — consistent with the polar result and confirming uniform approach to 0.
