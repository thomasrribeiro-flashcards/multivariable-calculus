+++
order = 10
tags = ["math", "multivariable-calculus", "double-integrals", "fubini", "polar-coordinates", "applications"]
+++

# Multivariable Calculus — Double Integrals

## 10.1 Motivating Problem: Volume Under a Surface

Q: Before defining the double integral, predict: how would you generalize the single-variable "area under a curve" idea to a surface $z = f(x, y)$ above a region $R$ in the $xy$-plane?
A: Slice $R$ into tiny rectangles of area $\Delta A$, erect a thin box of height $f(x, y)$ above each one, sum the box volumes $f(x_i, y_j)\,\Delta A$, and take the limit as the rectangles shrink. This gives the volume between the surface and the region — the natural 2D analogue of a Riemann sum.

Q: Why is the volume under $z = f(x, y)$ over a region $R$ a natural object to compute?
A: Many physical quantities — total mass, total charge, total rainfall over a county, average temperature over a plate — are obtained by summing a density-like quantity $f(x, y)$ over a 2D region. Each is a volume under some surface over $R$, so mastering this single computation solves a whole class of applied problems.

C: For a continuous nonnegative $f(x, y)$ on region $R$, the volume of the solid under $z = f(x, y)$ and above $R$ is given by the [double integral] $\iint_R f(x, y)\,dA$.

Q: What role does the region $R$ play that has no counterpart in single-variable integration?
A: In 1D, the "region" is just an interval $[a, b]$ — two numbers fix it. In 2D, $R$ can have curved boundaries, holes, or disconnected pieces, so describing $R$ (sketching it, finding its bounds) becomes a major part of every double integral problem. The shape of $R$ often dictates which coordinate system and which integration order to use.

## 10.2 Double Riemann Sum Over a Rectangle

Q: How is a rectangle $R = [a, b] \times [c, d]$ partitioned to set up a double Riemann sum, and why is this partition convenient?
A: Split $[a, b]$ into $m$ subintervals of width $\Delta x$ and $[c, d]$ into $n$ subintervals of width $\Delta y$, producing an $m \times n$ grid of subrectangles each with area $\Delta A = \Delta x\,\Delta y$. The grid is convenient because every subrectangle has the same shape, so the only per-cell variation is the sample point value $f(x_{ij}^*, y_{ij}^*)$.

C: A [double Riemann sum] over a rectangle is $\sum_{i=1}^{m} \sum_{j=1}^{n} f(x_{ij}^*, y_{ij}^*)\,\Delta A$, where $(x_{ij}^*, y_{ij}^*)$ is any sample point in the $ij$-th subrectangle and $\Delta A = \Delta x \, \Delta y$ is its area.

Q: Why does the choice of sample point $(x_{ij}^*, y_{ij}^*)$ not matter in the limit?
A: As the grid becomes infinitely fine, the variation of a continuous $f$ within each subrectangle shrinks to zero, so different sample choices (lower-left, center, max, min) all converge to the same value. This is exactly the 2D analogue of why left, right, and midpoint Riemann sums all give the same single-variable integral.

## 10.3 The Double Integral as a Limit

C: The [double integral] of $f$ over $R$ is defined as $\iint_R f(x, y)\,dA = \lim_{m, n \to \infty} \sum_{i=1}^{m}\sum_{j=1}^{n} f(x_{ij}^*, y_{ij}^*)\,\Delta A$, where the limit is taken so that the maximum subrectangle diameter tends to zero.

Q: What does the symbol $dA$ represent conceptually?
A: $dA$ is the infinitesimal area element — the limiting form of $\Delta A$ as the partition shrinks. In Cartesian coordinates $dA = dx\,dy$, but in polar coordinates $dA = r\,dr\,d\theta$. Thinking of $dA$ as "a tiny patch of area" is more portable across coordinate systems than writing $dx\,dy$ everywhere.

Q: When is a bounded function $f$ on $R$ guaranteed to be integrable over $R$?
A: If $f$ is continuous on $R$, or discontinuous only on a set of area zero (e.g., a finite union of smooth curves), then $\iint_R f\,dA$ exists. In practice, every function encountered in physics or geometry problems satisfies this, so existence is rarely the issue — setup is.

## 10.4 Iterated Integrals

C: An [iterated integral] over a rectangle $R = [a, b] \times [c, d]$ is $\int_a^b \int_c^d f(x, y)\,dy\,dx$, meaning: first integrate $f$ with respect to $y$ from $c$ to $d$ treating $x$ as constant, then integrate the resulting function of $x$ from $a$ to $b$.

Q: Why does the inner integral produce a function of the outer variable alone?
A: When integrating $\int_c^d f(x, y)\,dy$, $x$ is held fixed and plays the role of a parameter. The result is a definite integral whose value depends on $x$, i.e., a function $g(x) = \int_c^d f(x, y)\,dy$. The outer integral then integrates this $g(x)$ over $[a, b]$, reducing the 2D problem to two 1D problems.

Q: In $\int_a^b \int_c^d f(x, y)\,dy\,dx$, which $d$'s and limits match up, and why is this easy to get wrong?
A: The innermost differential $dy$ pairs with the innermost limits $c$ and $d$; the outer $dx$ pairs with $a$ and $b$. It's easy to get wrong because the limits are written in reverse order of evaluation — the outer pair appears first on the page but is integrated last. Always pair each differential with its adjacent limits.

## 10.5 Fubini's Theorem

C: [Fubini's theorem] states that if $f$ is continuous on the rectangle $R = [a, b] \times [c, d]$, then $\iint_R f(x, y)\,dA = \int_a^b \int_c^d f(x, y)\,dy\,dx = \int_c^d \int_a^b f(x, y)\,dx\,dy$.

Q: Why is Fubini's theorem the workhorse of double integration?
A: It guarantees that the abstract limit-of-Riemann-sum definition of $\iint_R f\,dA$ can be computed as two nested ordinary integrals, and that either order of integration gives the same answer. Without it, the double integral would be a theoretical object with no practical computation method.

Q: Under what hypothesis in this course does Fubini's theorem apply, and what can go wrong without it?
A: Continuity of $f$ on $R$ (or boundedness plus integrability) suffices. Without such a hypothesis, there exist pathological functions where the two iterated integrals give different finite values — so Fubini isn't a free pass, it's a theorem with conditions. In practice for smooth integrands, those conditions always hold.

Q: How can Fubini save you work on a hard-looking integral?
A: If one order of integration leads to an antiderivative you cannot express in closed form (e.g., $\int e^{-x^2}\,dx$), Fubini lets you try the other order, which may decouple the variables or eliminate the offending antiderivative. "Stuck? Swap the order" is a standard rescue move.

## 10.6 Type I Regions

C: A [Type I region] has the form $R = \{(x, y) : a \leq x \leq b,\ g_1(x) \leq y \leq g_2(x)\}$, where $g_1$ and $g_2$ are continuous functions giving the lower and upper $y$-boundaries as functions of $x$.

Q: For a Type I region, what is the iterated integral formula and why is $y$ integrated first?
A: $\iint_R f\,dA = \int_a^b \int_{g_1(x)}^{g_2(x)} f(x, y)\,dy\,dx$. $y$ is integrated first because its bounds depend on $x$; integrating $y$ while $x$ is held fixed collapses the vertical strip at position $x$ to a single number, leaving only $x$ for the outer integral, which must have constant bounds.

Q: Why must the outer limits of an iterated integral always be constants?
A: The final output of a definite integral is a number, not a function. If the outer bounds still contained variables, the overall integral would still be a function of those variables rather than a numerical value. So each successive integration must eliminate one variable, ending with pure constants outermost.

Q: Geometrically, how do you identify a Type I region from a sketch?
A: Draw a vertical line through $R$ at a typical $x$-value; if every such vertical line enters $R$ through one curve $y = g_1(x)$ and exits through another $y = g_2(x)$ without re-entering, $R$ is Type I. The shadow of $R$ on the $x$-axis gives the outer bounds $[a, b]$.

## 10.7 Type II Regions

C: A [Type II region] has the form $R = \{(x, y) : c \leq y \leq d,\ h_1(y) \leq x \leq h_2(y)\}$, where $h_1$ and $h_2$ give the left and right $x$-boundaries as functions of $y$.

Q: For a Type II region, what is the iterated integral formula?
A: $\iint_R f\,dA = \int_c^d \int_{h_1(y)}^{h_2(y)} f(x, y)\,dx\,dy$. Here $x$ is integrated first because its bounds depend on $y$; a horizontal slice at height $y$ runs from $x = h_1(y)$ to $x = h_2(y)$.

Q: How do you recognize a Type II region geometrically?
A: Draw a horizontal line through $R$ at a typical $y$-value; if it enters $R$ through one curve $x = h_1(y)$ and exits through $x = h_2(y)$ without re-entering, $R$ is Type II. The shadow of $R$ on the $y$-axis gives the outer bounds $[c, d]$.

Q: Can a region be both Type I and Type II, and what does that mean practically?
A: Yes — e.g., a disc, a rectangle, or the triangle $\{0 \leq x \leq 1,\ 0 \leq y \leq x\}$ is both. Practically, it means you have a genuine choice of integration order, and you should pick the one that makes either the integrand or the bounds simpler.

## 10.8 Switching the Order of Integration

Q: Why would you ever switch the order of integration if both orders give the same answer?
A: One order may produce an integrand with no elementary antiderivative (e.g., $\int e^{y^2}\,dy$) while the other gives something trivial; or one order may require splitting $R$ into several subregions while the other describes $R$ with one clean formula. The answer is the same, but the effort can differ enormously.

Q: What is the procedure for switching the order of integration?
A: 1) From the given bounds, sketch the region $R$. 2) Re-describe $R$ in the other type (Type I $\leftrightarrow$ Type II) by finding the new outer bounds (shadow on the other axis) and the new inner bounds (boundary curves solved for the other variable). 3) Rewrite the iterated integral with the new bounds. The integrand $f(x, y)$ itself is unchanged.

Q: Why is sketching $R$ essentially non-optional when switching order?
A: The algebraic bounds describe $R$ only implicitly; without a picture, it is very easy to swap bounds that happen to look symmetric but actually describe different shapes. The sketch lets you read off horizontal-slice bounds (Type II) from vertical-slice bounds (Type I) geometrically, which is far more reliable than algebraic manipulation alone.

## 10.9 Sketching the Region

Q: Why is sketching the region $R$ called "the single most important step" in setting up a double integral?
A: The bounds of an iterated integral are a literal description of $R$ in coordinates, so you cannot write correct bounds without knowing $R$'s shape. A sketch immediately reveals: which variable to integrate first, whether $R$ is Type I or II or must be split, and whether polar coordinates might help. Most double-integral errors trace back to skipping this sketch.

Q: What should a good region sketch include?
A: The boundary curves with their equations labeled, the intersection points of those curves (found by solving simultaneously), the shaded interior, and a representative vertical or horizontal slice showing how a typical integration variable enters and exits $R$. The intersection points usually become the outer integration bounds.

Q: When must you split a region $R$ into subregions before integrating?
A: When a single slice (vertical for Type I, horizontal for Type II) would enter and exit $R$ multiple times, or when different parts of the boundary have different functional forms on different intervals. Split $R$ along the problematic vertical/horizontal line so each piece is cleanly Type I or Type II, then add the integrals.

## 10.10 Linearity and Additivity

C: Double integrals are [linear]: $\iint_R (a f + b g)\,dA = a \iint_R f\,dA + b \iint_R g\,dA$ for any constants $a, b$ and integrable functions $f, g$.

C: Double integrals are [additive over regions]: if $R = R_1 \cup R_2$ and $R_1, R_2$ overlap only on their boundary (a set of area zero), then $\iint_R f\,dA = \iint_{R_1} f\,dA + \iint_{R_2} f\,dA$.

Q: Why is additivity over disjoint subregions the theoretical justification for "splitting a region"?
A: When $R$ is too awkward for one iterated integral, you decompose it into pieces $R_1, R_2, \dots$ that are each cleanly Type I or II, integrate each piece separately, and add. Additivity guarantees the sum equals the original integral — no correction terms for the shared boundaries since they have area zero.

Q: If $f(x, y) \geq g(x, y)$ everywhere on $R$, what inequality holds for their integrals and why?
A: $\iint_R f\,dA \geq \iint_R g\,dA$. Since every Riemann sum for $f$ is term-by-term at least the corresponding sum for $g$, the inequality is preserved in the limit. This is the monotonicity property, useful for bounding integrals you cannot compute exactly.

## 10.11 Area via Double Integral

C: The area of a region $R$ in the plane equals the double integral of the constant function 1 over $R$: $\text{area}(R) = [\iint_R 1\,dA]$.

Q: Why does integrating the constant 1 give area rather than some other quantity?
A: Geometrically, $\iint_R 1\,dA$ is the volume of a solid of height 1 standing over $R$ — a cylinder with base $R$ and height 1. Volume of such a cylinder equals (base area) × (height) = $\text{area}(R) \times 1 = \text{area}(R)$. So the double integral reduces to a pure area calculation when the integrand is 1.

Q: When is computing area via a double integral advantageous over a single-variable integral?
A: When $R$'s boundary is naturally given in both $x$- and $y$-forms, or when polar coordinates fit (circular/angular regions), the double-integral formulation avoids fiddly single-variable "top minus bottom" bookkeeping. It's also the natural way to express area in polar: $\iint_R r\,dr\,d\theta$.

## 10.12 Mass of a Lamina

C: If a thin plate (lamina) occupies region $R$ with density $\rho(x, y)$ (mass per unit area), its [total mass] is $m = \iint_R \rho(x, y)\,dA$, where $\rho(x, y)$ has units of mass/area and $dA$ has units of area, so the product has units of mass.

Q: Why does summing density times area element give mass?
A: On a tiny subregion of area $\Delta A$ where $\rho$ is nearly constant, the mass is approximately $\rho(x, y)\,\Delta A$. Summing over all subregions and taking the limit turns the sum into $\iint_R \rho\,dA$. This is the 2D analogue of "mass equals density times volume" — for a flat lamina, area plays the role of volume.

Q: What distinguishes uniform density from variable density for a lamina, and how does the mass formula simplify?
A: Uniform density means $\rho(x, y) = \rho_0$ is constant, so $m = \rho_0 \iint_R 1\,dA = \rho_0 \cdot \text{area}(R)$. Variable density $\rho(x, y)$ requires the full integral — common in textbook problems where density might depend on distance from an edge, e.g., $\rho = kx$ or $\rho = k(x^2 + y^2)$.

## 10.13 Center of Mass and Centroid

C: The [moments] of a lamina with density $\rho(x, y)$ about the coordinate axes are $M_x = \iint_R y\,\rho(x, y)\,dA$ and $M_y = \iint_R x\,\rho(x, y)\,dA$, where $M_x$ is the moment about the $x$-axis (uses $y$) and $M_y$ is the moment about the $y$-axis (uses $x$).

C: The [center of mass] of a lamina has coordinates $\bar x = \dfrac{M_y}{m}$ and $\bar y = \dfrac{M_x}{m}$, where $m$ is the total mass and $M_x, M_y$ are the moments about the coordinate axes.

Q: Why does the moment about the $x$-axis use a factor of $y$ (not $x$)?
A: The moment about an axis measures how much "leverage" each mass element exerts about that axis, weighted by its perpendicular distance from the axis. Distance to the $x$-axis is $|y|$, so each mass element $\rho\,dA$ contributes $y \cdot \rho\,dA$. This is the direct 2D extension of $M_x = \sum y_i m_i$ from point-mass mechanics.

Q: What is a centroid, and how does its formula differ from the center of mass?
A: The centroid is the center of mass when density is uniform (i.e., purely geometric). In that case $\rho$ cancels top and bottom: $\bar x = \dfrac{\iint_R x\,dA}{\iint_R 1\,dA}$ and similarly for $\bar y$. The centroid is a property of the shape alone, independent of material.

## 10.14 Moments of Inertia

C: The [moment of inertia] of a lamina about the $x$-axis is $I_x = \iint_R y^2\,\rho(x, y)\,dA$, where $y$ is the perpendicular distance from the mass element to the $x$-axis.

C: The [moment of inertia] of a lamina about the $y$-axis is $I_y = \iint_R x^2\,\rho(x, y)\,dA$, and about the origin (polar moment) is $I_0 = \iint_R (x^2 + y^2)\,\rho\,dA = I_x + I_y$.

Q: Why does moment of inertia use $y^2$ (squared) while first moment uses just $y$?
A: Moment of inertia measures resistance to rotational acceleration: kinetic energy of rotation is $\tfrac{1}{2} I \omega^2$, which requires summing $r^2$ times mass (where $r$ is perpendicular distance to the rotation axis). The squared distance comes from the $v = r\omega$ relation, so $v^2 \propto r^2$. First moments, by contrast, measure balance/leverage, which is linear in distance.

Q: What does a large moment of inertia physically mean for a rotating lamina?
A: A large $I$ means the lamina resists changes in rotation — it takes more torque to spin it up or slow it down. Mass farther from the axis contributes disproportionately (quadratically), which is why a figure skater spins faster by pulling arms in: same $m$, smaller $r^2$, smaller $I$, so $\omega$ grows to conserve angular momentum $L = I\omega$.

## 10.15 Average Value

C: The [average value] of $f$ over a region $R$ of positive area is $\bar f = \dfrac{1}{\text{area}(R)} \iint_R f(x, y)\,dA$, where $\text{area}(R) = \iint_R 1\,dA$.

Q: Why does this formula correctly generalize the single-variable $\bar f = \frac{1}{b-a}\int_a^b f\,dx$?
A: In 1D, $(b - a)$ is the "size" of the domain and the integral is the total "amount" of $f$ over it; dividing gives amount per unit size = average. In 2D, $\text{area}(R)$ is the size of the domain and $\iint_R f\,dA$ is the total amount, so dividing gives the 2D average by the same logic.

Q: Geometrically, what does $\bar f$ represent if $f \geq 0$?
A: $\bar f$ is the height of a flat-topped cylinder over $R$ that has the same volume as the solid under $z = f(x, y)$. In other words, if you could "level out" the surface to a constant height while preserving volume, that height is $\bar f$.

## 10.16 Why Polar Coordinates Help

Q: Why do polar coordinates dramatically simplify integrals over circular regions?
A: In Cartesian form, a disc boundary $x^2 + y^2 = a^2$ gives ugly bounds $y = \pm\sqrt{a^2 - x^2}$, creating square-root integrands. In polar, the same disc is just $0 \leq r \leq a$, $0 \leq \theta \leq 2\pi$ — constant bounds in a rectangle. Polar aligns the coordinate grid with the natural symmetry of the region.

Q: Besides circular regions, what types of integrands also cry out for polar coordinates?
A: Any integrand built from $x^2 + y^2$ (which becomes $r^2$), $\sqrt{x^2 + y^2}$ (becomes $r$), or $\arctan(y/x)$ (becomes $\theta$) simplifies dramatically. The classic example is $e^{-(x^2 + y^2)} = e^{-r^2}$, whose $r$-antiderivative $-\tfrac{1}{2}e^{-r^2}$ is elementary — unlike $e^{-x^2}$ in Cartesian form.

Q: How do you convert between Cartesian and polar coordinates?
A: $x = r\cos\theta$, $y = r\sin\theta$, so $x^2 + y^2 = r^2$. Conversely, $r = \sqrt{x^2 + y^2}$ and $\theta = \arctan(y/x)$ (with quadrant awareness). These substitutions rewrite the integrand; separately, the area element must also be changed.

## 10.17 The Polar Area Element

C: In polar coordinates, the infinitesimal area element is $dA = [r\,dr\,d\theta]$, not $dr\,d\theta$; the extra factor of $r$ is essential and forgetting it is the most common polar-integration mistake.

Q: In polar coordinates, what does the complete double integral conversion look like?
A: $\iint_R f(x, y)\,dA = \iint_{R'} f(r\cos\theta, r\sin\theta)\,r\,dr\,d\theta$, where $R'$ is the description of $R$ in $(r, \theta)$ coordinates. Three things change: the integrand (via $x = r\cos\theta$, $y = r\sin\theta$), the area element ($dA \to r\,dr\,d\theta$), and the bounds (in $r$ and $\theta$).

Q: Why is omitting the factor of $r$ so tempting, and how can you defend against the mistake?
A: It is tempting because $dA = dx\,dy$ in Cartesian looks like a simple product of differentials, so by analogy one writes $dA = dr\,d\theta$ in polar. Defense: always write $dA = r\,dr\,d\theta$ as a single unit before substituting, and remember the geometric argument that a polar "rectangle" at radius $r$ has side length $r\,d\theta$, not $d\theta$.

## 10.18 Why the Factor of $r$ Appears

Q: Give the geometric derivation of why $dA = r\,dr\,d\theta$ in polar coordinates.
A: Consider a small polar rectangle with sides $dr$ (radial) and $d\theta$ (angular) at radius $r$. The radial side has length $dr$. The angular side is an arc at radius $r$ sweeping angle $d\theta$, so its length is $r\,d\theta$ (arc length = radius × angle). The area of this nearly-rectangular patch is therefore $dr \cdot r\,d\theta = r\,dr\,d\theta$.

Q: What is the Jacobian explanation for the $r$ factor?
A: Under the change of variables $(x, y) = (r\cos\theta, r\sin\theta)$, the Jacobian determinant is $\left|\det \begin{pmatrix} \cos\theta & -r\sin\theta \\ \sin\theta & r\cos\theta \end{pmatrix}\right| = r\cos^2\theta + r\sin^2\theta = r$. The change-of-variables theorem then inserts $|J| = r$ into $dA$, giving $dA = r\,dr\,d\theta$ automatically.

Q: Intuitively, why does the area element grow with $r$?
A: At small $r$ (near the origin), a fixed angular sweep $d\theta$ covers only a tiny arc, so the polar rectangle is nearly a point. At large $r$, the same $d\theta$ sweeps a long arc $r\,d\theta$, so the polar rectangle has large area. The $r$ factor quantifies exactly this "fan spreads out as it gets longer" effect.

## 10.19 Setting Up Polar Double Integrals

Q: How do you describe a disc $x^2 + y^2 \leq a^2$ in polar coordinates?
A: $0 \leq r \leq a$ and $0 \leq \theta \leq 2\pi$. This is a rectangle in the $(r, \theta)$-plane — constant bounds, no functional dependencies — the ideal scenario for iterated integration.

Q: How do you describe an annulus $a^2 \leq x^2 + y^2 \leq b^2$ and a sector of a disc in polar?
A: Annulus: $a \leq r \leq b$, $0 \leq \theta \leq 2\pi$. Sector of a disc of radius $a$ between angles $\alpha$ and $\beta$: $0 \leq r \leq a$, $\alpha \leq \theta \leq \beta$. Both are rectangular in $(r, \theta)$, showcasing polar's natural fit for radially/angularly bounded shapes.

Q: For the disc of radius $a$ centered at the origin, how does the total area formula look in polar, and why is the $r$ factor now visible in the answer?
A: $\text{area} = \int_0^{2\pi}\int_0^a r\,dr\,d\theta = \int_0^{2\pi} \tfrac{a^2}{2}\,d\theta = \pi a^2$. The $r$ factor is what produces the $a^2/2$ after $r$-integration; without it you would get the wrong answer $a \cdot 2\pi$, which has units of length, not area.

Q: How do you decide whether to integrate $dr$ first or $d\theta$ first in polar?
A: If the radial bound depends on angle ($r$ ranges from 0 to some $r_{\max}(\theta)$, like a cardioid or a line $r = 2/\cos\theta$), integrate $dr$ first with $\theta$ constant. If $\theta$ ranges between two values depending on $r$, integrate $d\theta$ first. Sketching the region and drawing a radial ray (for $dr$-first) usually settles the order.

## 10.20 Worked Example: Non-Polar Double Integral

P: Compute $\iint_R (x + y)\,dA$, where $R$ is the region bounded by $y = x$ and $y = x^2$.

S:
**IDENTIFY**: Double integral over a region bounded by two curves. Non-circular region, polynomial integrand — use Cartesian coordinates. Need to determine region shape and integration order.

**PLAN**:
- Find intersection points of $y = x$ and $y = x^2$ to get outer bounds.
- Determine which curve is upper, which is lower, over that interval.
- Set up as Type I (integrate $dy$ first, from lower curve to upper curve, then $dx$ over the interval of intersection).

**EXECUTE**:
1. Intersections: $x = x^2 \Rightarrow x^2 - x = 0 \Rightarrow x(x - 1) = 0$, so $x = 0$ and $x = 1$. Curves meet at $(0, 0)$ and $(1, 1)$.
2. On $[0, 1]$: test $x = 1/2$; then $y = x = 0.5$ vs $y = x^2 = 0.25$. So $y = x$ is upper, $y = x^2$ is lower.
3. Set up Type I: $\iint_R (x + y)\,dA = \int_0^1 \int_{x^2}^{x} (x + y)\,dy\,dx$.
4. Inner integral: $\int_{x^2}^{x} (x + y)\,dy = \left[xy + \tfrac{y^2}{2}\right]_{y=x^2}^{y=x} = \left(x^2 + \tfrac{x^2}{2}\right) - \left(x \cdot x^2 + \tfrac{x^4}{2}\right) = \tfrac{3x^2}{2} - x^3 - \tfrac{x^4}{2}$.
5. Outer integral: $\int_0^1 \left(\tfrac{3x^2}{2} - x^3 - \tfrac{x^4}{2}\right) dx = \tfrac{3}{2}\cdot\tfrac{1}{3} - \tfrac{1}{4} - \tfrac{1}{2}\cdot\tfrac{1}{5} = \tfrac{1}{2} - \tfrac{1}{4} - \tfrac{1}{10}$.
6. Common denominator 20: $\tfrac{10}{20} - \tfrac{5}{20} - \tfrac{2}{20} = \tfrac{3}{20}$.

**EVALUATE**: $\iint_R (x + y)\,dA = \tfrac{3}{20}$. Sanity check: $R$ is a sliver-shaped region in the first quadrant contained in the unit square, with area $\int_0^1 (x - x^2)\,dx = \tfrac{1}{6}$. The integrand $x + y$ is at most 2 and at least 0 on $R$, so the integral must lie in $[0,\ 2 \cdot \tfrac{1}{6}] = [0, \tfrac{1}{3}]$. Our answer $\tfrac{3}{20} = 0.15$ sits safely inside — consistent.

## 10.21 Worked Example: Polar Double Integral

P: Compute $\iint_R e^{-(x^2 + y^2)}\,dA$, where $R$ is the unit disc $x^2 + y^2 \leq 1$.

S:
**IDENTIFY**: Integrand contains $x^2 + y^2$ and the region is a disc centered at the origin — both signal polar coordinates. In Cartesian form, the integrand $e^{-x^2}$ has no elementary antiderivative, so Cartesian is essentially impossible by hand.

**PLAN**:
- Convert integrand: $x^2 + y^2 = r^2 \Rightarrow e^{-(x^2+y^2)} = e^{-r^2}$.
- Convert area element: $dA = r\,dr\,d\theta$ (do NOT forget the $r$).
- Describe $R$ in polar: $0 \leq r \leq 1$, $0 \leq \theta \leq 2\pi$ (rectangular in $(r, \theta)$).
- Integrate $r$ first (inner), then $\theta$ (outer).

**EXECUTE**:
1. Rewrite: $\iint_R e^{-(x^2+y^2)}\,dA = \int_0^{2\pi} \int_0^1 e^{-r^2}\,r\,dr\,d\theta$.
2. Inner integral: $\int_0^1 e^{-r^2}\,r\,dr$. Substitute $u = -r^2$, $du = -2r\,dr \Rightarrow r\,dr = -\tfrac{1}{2}du$. When $r = 0$, $u = 0$; when $r = 1$, $u = -1$. So $\int_0^{-1} e^u \cdot (-\tfrac{1}{2})\,du = \tfrac{1}{2}\int_{-1}^{0} e^u\,du = \tfrac{1}{2}(1 - e^{-1})$.
3. Outer integral: $\int_0^{2\pi} \tfrac{1}{2}(1 - e^{-1})\,d\theta = \tfrac{1}{2}(1 - e^{-1}) \cdot 2\pi = \pi(1 - e^{-1})$.

**EVALUATE**: $\iint_R e^{-(x^2+y^2)}\,dA = \pi\left(1 - \tfrac{1}{e}\right) \approx \pi \cdot 0.632 \approx 1.986$. Sanity checks: (i) The integrand satisfies $0 < e^{-r^2} \leq 1$ on the disc, and the disc has area $\pi$, so the integral must lie in $(0, \pi] \approx (0, 3.14]$ — our answer fits. (ii) The $r$ factor was the key — without it we'd have gotten the wrong value and missed the elementary antiderivative entirely, because $\int e^{-r^2}\,dr$ alone has no closed form but $\int e^{-r^2}\,r\,dr$ does. (iii) This integral is the foundation of the classic Gaussian $\int_{-\infty}^{\infty} e^{-x^2}\,dx = \sqrt{\pi}$ trick: letting $R$ become the whole plane gives $\pi$, whose square root is the famous result.
