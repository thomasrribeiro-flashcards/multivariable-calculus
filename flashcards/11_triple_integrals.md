+++
order = 11
tags = ["math", "multivariable-calculus", "triple-integrals", "cylindrical", "spherical", "volume", "moments"]
+++

# Multivariable Calculus — Triple Integrals

## 11.1 Extending Integration to 3D Regions

Q: Why extend double integrals to triple integrals over solid regions $E\subset\mathbb{R}^3$?
A: Many physical quantities — mass, charge, probability, work done against a 3D force field — live on solids, not flat sheets. A triple integral $\iiint_E f\,dV$ is the natural tool to sum a density $f(x,y,z)$ over a volume, just as a double integral sums a surface density over an area.

Q: Before seeing the formal definition, predict: what should $\iiint_E 1\,dV$ equal?
A: The volume of $E$. Integrating density $1$ over a region should just add up infinitesimal volume elements $dV$, recovering the total volume — the 3D analogue of $\iint_D 1\,dA = \text{area}(D)$.

C: A triple integral over a solid $E\subset\mathbb{R}^3$ generalizes the double integral by integrating a function of [three variables] over a 3D region.

## 11.2 Definition as a Limit of Riemann Sums

Q: How is $\iiint_E f(x,y,z)\,dV$ defined as a Riemann sum?
A: Enclose $E$ in a box, partition it into sub-boxes of volumes $\Delta V_{ijk}$, pick sample points $(x_{ijk}^*,y_{ijk}^*,z_{ijk}^*)\in E$, and form $\sum f(x_{ijk}^*,y_{ijk}^*,z_{ijk}^*)\,\Delta V_{ijk}$. The triple integral is the limit as the norm of the partition (largest sub-box diagonal) tends to $0$, provided the limit exists.

C: The triple integral is defined as $\iiint_E f\,dV = \lim_{\|P\|\to 0}\sum_{i,j,k} f(x_{ijk}^*,y_{ijk}^*,z_{ijk}^*)\,[\Delta V_{ijk}]$, where $\Delta V_{ijk}$ is the volume of a sub-box.

Q: Why is continuity of $f$ on a closed bounded region $E$ enough to guarantee $\iiint_E f\,dV$ exists?
A: A continuous function on a closed bounded set is uniformly continuous and bounded, so Riemann sums converge independently of the partition choice and sample points. This mirrors 1D and 2D integrability theorems.

## 11.3 Iterated Triple Integral Over a Box

Q: What does Fubini's theorem say for a triple integral over a box $B=[a,b]\times[c,d]\times[p,q]$?
A: If $f$ is continuous on $B$, then $\iiint_B f\,dV$ equals any of the six iterated integrals, e.g. $\int_a^b\!\int_c^d\!\int_p^q f(x,y,z)\,dz\,dy\,dx$. The order of integration doesn't change the value, only the computation.

C: On a box $B=[a,b]\times[c,d]\times[p,q]$, $\iiint_B f\,dV = \int_a^b\!\int_c^d\!\int_p^q [f(x,y,z)]\,dz\,dy\,dx$ for continuous $f$.

P: Compute $\iiint_B xyz\,dV$ where $B=[0,1]\times[0,2]\times[0,3]$.

S:
**IDENTIFY**: Triple integral over a rectangular box with separable integrand $xyz$.

**PLAN**: Because $B$ is a product and the integrand factors as $x\cdot y\cdot z$, the triple integral splits into a product of three single integrals.

**EXECUTE**:
1. $\iiint_B xyz\,dV = \left(\int_0^1 x\,dx\right)\left(\int_0^2 y\,dy\right)\left(\int_0^3 z\,dz\right)$.
2. Compute each: $\int_0^1 x\,dx = \tfrac{1}{2}$, $\int_0^2 y\,dy = 2$, $\int_0^3 z\,dz = \tfrac{9}{2}$.
3. Multiply: $\tfrac{1}{2}\cdot 2\cdot\tfrac{9}{2} = \tfrac{9}{2}$.

**EVALUATE**: Positive integrand on a positive-coordinate box gives a positive answer; dimensions $[\text{length}]^3\cdot[\text{length}]^3$ match an $xyz$-weighted volume.

## 11.4 Type 1 Regions

Q: What is a Type 1 region in $\mathbb{R}^3$, and how do we integrate over it?
A: A Type 1 region has $z$ bounded by two surfaces: $E=\{(x,y,z): (x,y)\in D,\ u_1(x,y)\le z\le u_2(x,y)\}$, where $D$ is the projection of $E$ onto the $xy$-plane. Integrate $z$ first: $\iiint_E f\,dV = \iint_D\!\int_{u_1(x,y)}^{u_2(x,y)} f(x,y,z)\,dz\,dA$.

C: For a Type 1 region, $\iiint_E f\,dV = \iint_D\!\int_{u_1(x,y)}^{[u_2(x,y)]} f(x,y,z)\,dz\,dA$, where $D$ is the projection onto the $xy$-plane.

Q: Why must the inner $z$-bounds $u_1(x,y)$ and $u_2(x,y)$ depend only on $x$ and $y$ (not $z$)?
A: The inner integral fixes $(x,y)$ and sweeps $z$ through a vertical segment inside $E$. The endpoints of that segment are determined by where the vertical line pierces the boundary, which depends on $(x,y)$ alone — $z$ is the variable being integrated.

## 11.5 Type 2 and Type 3 Regions

C: A [Type 2] region has $x$ bounded by two functions of $(y,z)$: $E=\{(x,y,z):(y,z)\in D,\ u_1(y,z)\le x\le u_2(y,z)\}$, projected onto the $yz$-plane.

C: A [Type 3] region has $y$ bounded by two functions of $(x,z)$: $E=\{(x,y,z):(x,z)\in D,\ u_1(x,z)\le y\le u_2(x,z)\}$, projected onto the $xz$-plane.

Q: Why do we bother distinguishing Type 1, 2, and 3 regions rather than always projecting onto the $xy$-plane?
A: The projection onto $xy$ may give complicated $z$-bounds (e.g., multiple pieces), while projecting onto another plane can yield a simpler description. Choosing the right type minimizes case splits and often makes the inner integral analytically tractable.

## 11.6 Setting Up Bounds: Project and Slice

Q: What is the general procedure for setting up triple integral bounds over a Type 1 region?
A: (i) Sketch $E$; (ii) decide which variable will be integrated innermost (here $z$); (iii) find the two surfaces $z=u_1(x,y)$ (bottom) and $z=u_2(x,y)$ (top) bounding $E$ vertically; (iv) project $E$ onto the $xy$-plane to obtain $D$; (v) set up $D$ as a 2D Type I or Type II region and write the iterated integral.

P: Set up (don't evaluate) $\iiint_E f\,dV$ where $E$ is bounded by the planes $x=0$, $y=0$, $z=0$, and $x+y+z=1$.

S:
**IDENTIFY**: Tetrahedron in the first octant; natural Type 1 setup with $z$ on top bounded by $z=1-x-y$.

**PLAN**: Choose $z$ as innermost. Project onto the $xy$-plane to find $D$ by setting $z=0$ in the slanted plane.

**EXECUTE**:
1. Vertical bounds: $0\le z\le 1-x-y$.
2. Projection $D$ onto $xy$-plane: the triangle with $x\ge 0$, $y\ge 0$, $x+y\le 1$.
3. Describe $D$: $0\le x\le 1$, $0\le y\le 1-x$.
4. Final form: $\int_0^1\!\int_0^{1-x}\!\int_0^{1-x-y} f(x,y,z)\,dz\,dy\,dx$.

**EVALUATE**: Each bound is a function of the outer variables only — valid iterated form. Plugging $f\equiv 1$ should give the tetrahedron's volume $\tfrac{1}{6}$, a good sanity test.

## 11.7 Order of Integration

Q: Why can we change the order of integration in a triple integral, and what must we be careful about?
A: By Fubini's theorem the value is independent of order for continuous $f$ on a nice region. But the bounds must be rewritten to describe the same solid $E$ in the new order — simply swapping $dz\,dy\,dx$ to $dy\,dx\,dz$ without redoing the limits gives a wrong answer.

C: Changing the order of integration in a triple integral is allowed by [Fubini's theorem], but requires rewriting the bounds to describe the same region.

Q: When might you switch the order of integration in practice?
A: When the current order leads to an antiderivative you cannot compute in closed form, or when the bounds in the current order require splitting the region into multiple pieces. A reordering can sometimes turn the integral into a standard one-variable integral.

## 11.8 Volume as a Triple Integral

C: The volume of a solid $E$ is $V = \iiint_E [1]\,dV$.

Q: Why does $\iiint_E 1\,dV$ equal the volume of $E$?
A: Each Riemann sum term is $1\cdot\Delta V_{ijk} = \Delta V_{ijk}$, so the sum is the total volume of sub-boxes intersecting $E$. In the limit, sub-boxes fit $E$ exactly and the sum converges to the volume.

## 11.9 Mass, Center of Mass, and Moments

Q: If a solid $E$ has mass density $\rho(x,y,z)$, how do we compute its total mass $m$?
A: Mass is the integral of density over the region: $m = \iiint_E \rho(x,y,z)\,dV$. Each infinitesimal piece contributes $\rho\,dV$ (mass = density $\times$ volume), summed over $E$.

C: The mass of a solid $E$ with density $\rho(x,y,z)$ is $m = \iiint_E [\rho(x,y,z)]\,dV$.

C: The moment of $E$ about the $yz$-plane is $M_{yz} = \iiint_E [x]\,\rho(x,y,z)\,dV$, where $x$ is the signed distance to the $yz$-plane and $\rho$ is the mass density.

C: The center of mass of a solid $E$ has $x$-coordinate $\bar{x} = [M_{yz}/m]$, where $M_{yz}=\iiint_E x\rho\,dV$ and $m$ is total mass.

Q: Why is the center of mass defined as a density-weighted average of position, not a plain average?
A: In a non-uniform solid, denser regions should "pull" the balance point toward them. Weighting position by $\rho\,dV$ (an infinitesimal mass element) captures this; dividing by total mass normalizes to get an actual coordinate.

## 11.10 Moment of Inertia

Q: What is the moment of inertia of a solid $E$ about the $z$-axis?
A: $I_z = \iiint_E (x^2+y^2)\,\rho(x,y,z)\,dV$, where $x^2+y^2$ is the squared perpendicular distance from $(x,y,z)$ to the $z$-axis and $\rho$ is the mass density. It measures rotational inertia about that axis.

C: Moment of inertia about the $z$-axis: $I_z = \iiint_E [(x^2+y^2)]\,\rho(x,y,z)\,dV$, with $\rho$ the mass density.

Q: Why does moment of inertia use the squared distance to the axis, not the distance itself?
A: Rotational kinetic energy of a mass element is $\tfrac{1}{2}(dm)v^2=\tfrac{1}{2}(dm)(\omega r)^2 = \tfrac{1}{2}\omega^2 r^2\,dm$. Integrating pulls out $\tfrac{1}{2}\omega^2$, leaving $\int r^2\,dm$ — a quadratic dependence on distance $r$.

## 11.11 Cylindrical Coordinates

C: In cylindrical coordinates $(r,\theta,z)$: $x=r\cos\theta$, $y=r\sin\theta$, $z=z$, with volume element $dV = [r\,dr\,d\theta\,dz]$.

Q: Why does the cylindrical volume element carry the factor $r$?
A: It is the Jacobian of the change of variables from $(x,y,z)$ to $(r,\theta,z)$. Geometrically, an infinitesimal wedge has radial width $dr$, arc length $r\,d\theta$, and height $dz$, giving volume $r\,dr\,d\theta\,dz$.

C: In cylindrical coordinates, $r^2 = [x^2+y^2]$ and $\tan\theta = y/x$; $z$ is unchanged.

## 11.12 When Cylindrical Coordinates Help

Q: When are cylindrical coordinates the right choice for a triple integral?
A: When the region has axial symmetry about the $z$-axis (cylinders, paraboloids, cones with vertical axis) or when the integrand depends only on $x^2+y^2$ and $z$. Then $r$ and $z$ bounds are clean and $\theta$ ranges over a full or partial circle.

Q: Why do cylinders and paraboloids simplify dramatically in cylindrical coordinates?
A: A cylinder $x^2+y^2=a^2$ becomes $r=a$, and a paraboloid $z=x^2+y^2$ becomes $z=r^2$. One equation, one variable — the boundary description is trivial and independent of $\theta$.

## 11.13 Spherical Coordinates

C: In spherical coordinates $(\rho,\theta,\phi)$: $x=[\rho\sin\phi\cos\theta]$, $y=\rho\sin\phi\sin\theta$, $z=\rho\cos\phi$, where $\rho\ge 0$ is distance from origin, $\phi\in[0,\pi]$ is the polar angle from the $+z$-axis, and $\theta\in[0,2\pi)$ is the azimuth.

C: The spherical volume element is $dV = [\rho^2\sin\phi]\,d\rho\,d\phi\,d\theta$.

Q: What is the range of each spherical coordinate and why?
A: $\rho\in[0,\infty)$ (distance, non-negative), $\phi\in[0,\pi]$ (polar angle from $+z$-axis, covers north-to-south), and $\theta\in[0,2\pi)$ (azimuth, one full rotation around the $z$-axis). Together they parameterize $\mathbb{R}^3$ once (up to the axis).

## 11.14 Conventions for Spherical Coordinates

Q: Why is it important to state which spherical convention you're using?
A: Math texts commonly use $(\rho,\theta,\phi)$ with $\phi$ from the $+z$-axis, while physics/engineering texts use $(r,\theta,\phi)$ with $\theta$ from the $+z$-axis and $\phi$ for azimuth. Swapping the angles' roles flips $\sin$ and $\cos$ in the Jacobian and in the coordinate formulas — guaranteeing wrong answers if mixed.

C: In the math convention used here, $\phi$ is measured from the [positive $z$-axis] and $\theta$ is the azimuthal angle in the $xy$-plane.

## 11.15 Why the $\rho^2\sin\phi$ Factor

Q: Why does the spherical Jacobian equal $\rho^2\sin\phi$?
A: A spherical "box" has radial thickness $d\rho$, polar arc $\rho\,d\phi$, and azimuthal arc $(\rho\sin\phi)\,d\theta$ (radius of the latitude circle is $\rho\sin\phi$). Multiplying these three orthogonal lengths gives $\rho^2\sin\phi\,d\rho\,d\phi\,d\theta$. Equivalently, it's $|\det J|$ for the coordinate map.

Q: Why does the spherical Jacobian vanish at $\phi=0$ and $\phi=\pi$?
A: Those are the north and south poles — the latitude circle shrinks to a point, so an azimuthal increment $d\theta$ contributes no arc length. $\sin\phi=0$ there, giving zero volume element: the coordinates are degenerate at the axis.

## 11.16 When Spherical Coordinates Help

Q: When should you reach for spherical coordinates?
A: When the region has spherical symmetry about the origin (balls, spherical shells, cones with vertex at origin) or when the integrand depends only on $\rho=\sqrt{x^2+y^2+z^2}$. Then $\rho$ bounds become constants or simple functions, and angular integrals often decouple.

C: A sphere of radius $a$ centered at the origin is described in spherical coordinates as [$\rho = a$], with $\phi\in[0,\pi]$ and $\theta\in[0,2\pi)$.

Q: Why does a cone with vertex at the origin have a simple spherical description?
A: A cone $z=\sqrt{x^2+y^2}$ is the set of points making a fixed angle with the $+z$-axis. In spherical coordinates that's $\phi=\pi/4$ — a single angular equation, just as a plane through the origin is described by fixing one angle.

## 11.17 Choosing the Right Coordinate System

Q: How do you decide which coordinate system to use for a triple integral?
A: Match BOTH the region's symmetry AND the integrand's structure. If both are cylindrically symmetric about an axis, use cylindrical. If both point to the origin, use spherical. If neither, Cartesian is often simpler. A "clever" coordinate change hurts if it only simplifies one of the two.

C: Choose cylindrical coordinates when the region and integrand respect [axial symmetry about the $z$-axis]; spherical when they respect [spherical symmetry about the origin].

Q: Why can a poor coordinate choice make a triple integral much harder?
A: You might get a simple region but an integrand like $\sin(\rho^2\sin^2\phi)$ that has no elementary antiderivative; or a clean integrand on a region requiring three case splits. Each coordinate system trades off region description against integrand form.

## 11.18 Worked Example: Cylindrical Coordinates

P: Compute $\iiint_E z\,dV$ where $E$ is bounded above by the paraboloid $z=4-x^2-y^2$ and below by $z=0$.

S:
**IDENTIFY**: Region is axially symmetric about the $z$-axis (paraboloid cap), integrand depends only on $z$ — cylindrical coordinates are ideal.

**PLAN**: Convert to $(r,\theta,z)$. The paraboloid becomes $z=4-r^2$; the base is the disk $x^2+y^2\le 4$, i.e. $0\le r\le 2$, $0\le\theta\le 2\pi$. Use $z$ as innermost, $0\le z\le 4-r^2$. Don't forget $dV=r\,dr\,d\theta\,dz$.

**EXECUTE**:
1. $\iiint_E z\,dV = \int_0^{2\pi}\!\int_0^2\!\int_0^{4-r^2} z\cdot r\,dz\,dr\,d\theta$.
2. Inner: $\int_0^{4-r^2} z\,dz = \tfrac{1}{2}(4-r^2)^2$.
3. Middle: $\int_0^2 \tfrac{r}{2}(4-r^2)^2\,dr$. Let $u=4-r^2$, $du=-2r\,dr$, so $\tfrac{r}{2}dr = -\tfrac{1}{4}du$. Bounds $r=0\to u=4$, $r=2\to u=0$. Integral becomes $-\tfrac{1}{4}\int_4^0 u^2\,du = \tfrac{1}{4}\int_0^4 u^2\,du = \tfrac{1}{4}\cdot\tfrac{64}{3}=\tfrac{16}{3}$.
4. Outer: $\int_0^{2\pi}\tfrac{16}{3}\,d\theta = \tfrac{32\pi}{3}$.

**EVALUATE**: Positive integrand over a positive region gives a positive answer. The $2\pi$ factor confirms full axial symmetry. Units: $[\text{length}]^4$, consistent with $z\cdot dV$.

## 11.19 Worked Example: Spherical Coordinates

P: Find the volume of the solid $E$ bounded above by the sphere $x^2+y^2+z^2=4$ and below by the cone $z=\sqrt{x^2+y^2}$.

S:
**IDENTIFY**: Spherical symmetry about origin; cone with vertex at origin — spherical coordinates are ideal. Volume means integrand is $1$.

**PLAN**: Sphere: $\rho=2$. Cone $z=\sqrt{x^2+y^2}$ makes a $45^\circ$ angle with $+z$-axis, so $\phi=\pi/4$. Region is "ice-cream cone" above the cone, inside the sphere: $0\le\rho\le 2$, $0\le\phi\le\pi/4$, $0\le\theta\le 2\pi$. Use $dV=\rho^2\sin\phi\,d\rho\,d\phi\,d\theta$.

**EXECUTE**:
1. $V = \int_0^{2\pi}\!\int_0^{\pi/4}\!\int_0^2 \rho^2\sin\phi\,d\rho\,d\phi\,d\theta$.
2. Inner (in $\rho$): $\int_0^2 \rho^2\,d\rho = \tfrac{8}{3}$.
3. Middle (in $\phi$): $\int_0^{\pi/4}\sin\phi\,d\phi = 1-\cos(\pi/4) = 1-\tfrac{\sqrt{2}}{2}$.
4. Outer (in $\theta$): $\int_0^{2\pi} d\theta = 2\pi$.
5. Multiply: $V = \tfrac{8}{3}\cdot\left(1-\tfrac{\sqrt{2}}{2}\right)\cdot 2\pi = \tfrac{16\pi}{3}\left(1-\tfrac{\sqrt{2}}{2}\right)$.

**EVALUATE**: Positive result, less than the full ball volume $\tfrac{32\pi}{3}$ as expected (we kept only the cap above the cone). Numerically $\approx 4.91$, a reasonable fraction of the ball's $\approx 33.5$.
