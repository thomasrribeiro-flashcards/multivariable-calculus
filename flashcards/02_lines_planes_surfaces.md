+++
order = 2
tags = ["math", "multivariable-calculus", "lines", "planes", "quadric-surfaces", "cylindrical", "spherical"]
+++

# Multivariable Calculus — Lines, Planes, and Surfaces in Space

## 2.1 Why Parametric/Vector Forms for Lines in 3D

Q: Why can't we describe a line in 3D with a single equation like $y = mx + b$?
A: In 3D, a single linear equation defines a plane, not a line. A line has only one degree of freedom, so we need a parameter $t$ that traces out points along it, or two simultaneous equations whose intersection is the line.

Q: Why does "slope" fail as a concept for lines in 3D?
A: Slope assumes a single rise-over-run ratio, but in 3D a line has rates of change in $x$, $y$, and $z$ simultaneously. We replace slope with a direction vector $\vec{v} = \langle a, b, c\rangle$ that captures all three rates at once.

C: In 3D, a line is specified by a [point] on it and a [direction vector] parallel to it.

Q: Before seeing the formula, predict: what is the minimum data needed to uniquely determine a line in 3D?
A: One point (to anchor it) plus a direction (to orient it). Two points also work, because their difference gives the direction.

## 2.2 Vector Equation of a Line

C: The vector equation of a line through point $\vec{r}_0$ with direction $\vec{v}$ is [$\vec{r}(t) = \vec{r}_0 + t\vec{v}$], where $\vec{r}(t)$ is the position vector of a point on the line and $t \in \mathbb{R}$ is the parameter.

Q: In $\vec{r}(t) = \vec{r}_0 + t\vec{v}$, what geometric role does each term play?
A: $\vec{r}_0$ anchors the line at a fixed basepoint, and $t\vec{v}$ is a displacement along the direction vector. Varying $t$ slides the tip of $\vec{r}(t)$ along the line; $t=0$ gives the basepoint.

Q: Why are direction vectors for a line not unique?
A: Any nonzero scalar multiple $k\vec{v}$ points along the same line. The direction is a line through the origin in direction-space, so only the direction (up to scaling) matters, not the magnitude.

C: If $\vec{v}$ is a direction vector of a line, then [$k\vec{v}$] for any nonzero scalar $k$ is also a valid direction vector.

## 2.3 Parametric Equations of a Line

C: The parametric equations of a line through $(x_0, y_0, z_0)$ with direction $\langle a, b, c\rangle$ are [$x = x_0 + at$], [$y = y_0 + bt$], and $z = z_0 + ct$, where $t$ is the scalar parameter.

Q: How do parametric equations relate to the vector equation $\vec{r}(t) = \vec{r}_0 + t\vec{v}$?
A: They are just the component-wise version. Writing $\vec{r}_0 = \langle x_0, y_0, z_0\rangle$ and $\vec{v} = \langle a,b,c\rangle$ and equating components gives three scalar equations in $t$.

Q: Why is the parameter $t$ useful beyond just describing a static line?
A: It naturally encodes motion along the line: at $t=0$ you are at $\vec{r}_0$, and as $t$ increases you move in the direction of $\vec{v}$. This is why parametric form is the starting point for describing curves and trajectories.

## 2.4 Symmetric Equations of a Line

C: Solving each parametric equation for $t$ and equating yields the symmetric form [$\dfrac{x - x_0}{a} = \dfrac{y - y_0}{b} = \dfrac{z - z_0}{c}$], valid when $a, b, c$ are all nonzero.

Q: Why do symmetric equations fail when a direction component is zero?
A: If $a = 0$, you can't divide by $a$. Geometrically, the line is constant in $x$ (i.e., $x = x_0$), so you replace that fraction with the equation $x = x_0$ and write symmetric form only for the remaining coordinates.

Q: What does the symmetric form reveal that the parametric form hides?
A: It eliminates the parameter, showing the line as the intersection of two planes (each equality between fractions is one planar equation). This makes it clearer that a line in 3D is defined by two simultaneous linear constraints.

C: If the direction vector has $a = 0$, the symmetric form becomes [$x = x_0$] together with $\dfrac{y - y_0}{b} = \dfrac{z - z_0}{c}$.

## 2.5 Line Through Two Points

Q: Given two points $P$ and $Q$, how do you construct a direction vector for the line through them?
A: Take the displacement $\vec{v} = \vec{PQ} = Q - P$. This vector points from $P$ to $Q$ and lies along the line, so it serves as a valid direction vector.

C: The line through points $P$ and $Q$ has direction vector [$\vec{PQ} = Q - P$], and can be parameterized as $\vec{r}(t) = P + t(Q - P)$.

Q: In the parameterization $\vec{r}(t) = P + t(Q - P)$, what are the values of $t$ at $P$ and $Q$?
A: $t = 0$ gives $\vec{r}(0) = P$, and $t = 1$ gives $\vec{r}(1) = Q$. Values $0 \le t \le 1$ trace the segment $\overline{PQ}$; values outside extend the line beyond.

## 2.6 Distance from a Point to a Line

C: The distance from point $Q$ to the line through $P$ with direction $\vec{v}$ is [$d = \dfrac{\|\vec{PQ} \times \vec{v}\|}{\|\vec{v}\|}$], where $\vec{PQ} = Q - P$ and $\times$ is the cross product.

Q: Why does the cross product give the perpendicular distance from a point to a line?
A: $\|\vec{PQ} \times \vec{v}\| = \|\vec{PQ}\|\,\|\vec{v}\|\sin\theta$, where $\theta$ is the angle between $\vec{PQ}$ and $\vec{v}$. The quantity $\|\vec{PQ}\|\sin\theta$ is exactly the perpendicular component of $\vec{PQ}$ to the line, so dividing by $\|\vec{v}\|$ isolates it.

Q: Geometrically, what area does $\|\vec{PQ} \times \vec{v}\|$ represent, and how does that give distance?
A: It is the area of the parallelogram spanned by $\vec{PQ}$ and $\vec{v}$. Area = base × height, with base $\|\vec{v}\|$ and height = perpendicular distance from $Q$ to the line. Dividing area by base yields the height.

## 2.7 Classifying Two Lines in Space

Q: What are the three possible relationships between two lines in 3D?
A: (1) Parallel — direction vectors are scalar multiples, lines never meet (or coincide). (2) Intersecting — not parallel, and there exist parameter values giving a common point. (3) Skew — not parallel and do not intersect (only possible in 3D).

Q: How do you test whether two lines are parallel?
A: Check whether their direction vectors $\vec{v}_1$ and $\vec{v}_2$ are scalar multiples, equivalently $\vec{v}_1 \times \vec{v}_2 = \vec{0}$. If yes, pick a point on one line and check if it lies on the other to distinguish parallel-and-distinct from coincident.

Q: How do you test whether two non-parallel lines intersect or are skew?
A: Set the two parametric forms equal and solve the resulting system for the parameters $t, s$. If a consistent solution exists, the lines intersect at that point; if the system is inconsistent, the lines are skew.

C: Two lines in 3D that are neither parallel nor intersecting are called [skew], a configuration that cannot occur in 2D.

## 2.8 Scalar Equation of a Plane

C: The scalar (point-normal) equation of a plane through $(x_0, y_0, z_0)$ with normal vector $\vec{n} = \langle a, b, c\rangle$ is [$a(x - x_0) + b(y - y_0) + c(z - z_0) = 0$].

Q: How does the point-normal equation follow from the dot product?
A: A point $(x,y,z)$ lies on the plane iff the displacement from the anchor $(x_0,y_0,z_0)$ is perpendicular to $\vec{n}$. Writing this as $\vec{n} \cdot \langle x-x_0, y-y_0, z-z_0\rangle = 0$ expands to the scalar form.

C: Expanding the point-normal form gives the general form [$ax + by + cz + d = 0$], where $d = -(ax_0 + by_0 + cz_0)$ and $\langle a,b,c\rangle$ is still the normal vector.

## 2.9 A Plane is Determined by a Point and a Normal

Q: Why is a single point and a normal vector enough to determine a unique plane?
A: The normal fixes the plane's orientation (tilt) in space, and the point pins down its location along that normal direction. Without the point, infinitely many parallel planes share the normal; without the normal, infinitely many planes pass through the point.

Q: Why are two non-parallel vectors in a plane equivalent information to a normal vector?
A: Because the cross product of two non-parallel in-plane vectors produces a normal. So "a point plus two spanning vectors" and "a point plus a normal" carry the same geometric data.

C: The normal vector of a plane is [perpendicular] to every vector lying in the plane.

## 2.10 Finding a Normal from Two In-Plane Vectors

C: If $\vec{u}$ and $\vec{v}$ are two non-parallel vectors lying in a plane, then a normal vector is [$\vec{n} = \vec{u} \times \vec{v}$], where $\times$ is the cross product.

Q: Why does the cross product of two vectors in a plane produce a valid normal?
A: By definition, $\vec{u} \times \vec{v}$ is perpendicular to both $\vec{u}$ and $\vec{v}$. Since these two vectors span the plane, any vector perpendicular to both is perpendicular to the entire plane, i.e., a normal.

Q: What happens if you compute $\vec{u} \times \vec{v}$ when $\vec{u}$ and $\vec{v}$ are parallel?
A: The cross product is $\vec{0}$, which gives no directional information. Geometrically, parallel vectors don't span a plane — they span only a line — so no unique plane is determined.

## 2.11 Plane Through Three Non-Collinear Points

P: How do you find the equation of a plane passing through three given non-collinear points $P$, $Q$, $R$?

S:
**IDENTIFY**: Determine a plane from three points in space.

**PLAN**:
- Form two vectors lying in the plane: $\vec{u} = \vec{PQ}$ and $\vec{v} = \vec{PR}$.
- Compute the normal $\vec{n} = \vec{u} \times \vec{v}$.
- Use $\vec{n}$ with any of the three points in the point-normal equation.

**EXECUTE**:
1. Compute $\vec{u} = Q - P$ and $\vec{v} = R - P$.
2. Compute $\vec{n} = \vec{u} \times \vec{v} = \langle a, b, c\rangle$.
3. Write $a(x - x_P) + b(y - y_P) + c(z - z_P) = 0$.
4. Simplify to general form $ax + by + cz + d = 0$.

**EVALUATE**:
- Verify all three points satisfy the final equation.
- If $\vec{n} = \vec{0}$, the points are collinear and no unique plane exists.

Q: Why must the three points be non-collinear to determine a plane?
A: Three collinear points all lie on infinitely many planes (the line can be rotated about itself). Non-collinearity ensures $\vec{PQ}$ and $\vec{PR}$ are not parallel, so their cross product is nonzero and the plane is unique.

## 2.12 Distance from a Point to a Plane

C: The distance from point $(x_0, y_0, z_0)$ to the plane $ax + by + cz + d = 0$ is [$D = \dfrac{|ax_0 + by_0 + cz_0 + d|}{\sqrt{a^2 + b^2 + c^2}}$], where $\langle a,b,c\rangle$ is the plane's normal.

Q: Why does the distance formula use the absolute value of $ax_0 + by_0 + cz_0 + d$?
A: The signed quantity indicates which side of the plane the point is on (positive vs. negative). Distance is a non-negative magnitude, so we take the absolute value to discard the side information.

Q: Why do we divide by $\sqrt{a^2 + b^2 + c^2}$ in the distance-to-plane formula?
A: That factor is $\|\vec{n}\|$. The numerator $|ax_0+by_0+cz_0+d|$ is the unnormalized projection of the displacement onto $\vec{n}$; dividing by $\|\vec{n}\|$ converts it into an actual Euclidean length.

Q: What is the geometric derivation of the point-to-plane distance formula?
A: Pick any point $P_1$ on the plane; then $\vec{P_1 P_0}$ is a displacement. The distance is the length of its projection onto the unit normal $\hat{n}$: $D = |\vec{P_1 P_0} \cdot \hat{n}|$. Expanding in coordinates yields the standard formula.

## 2.13 Angle Between Two Planes

C: The angle $\theta$ between two planes equals the angle between their normal vectors, given by [$\cos\theta = \dfrac{|\vec{n}_1 \cdot \vec{n}_2|}{\|\vec{n}_1\|\,\|\vec{n}_2\|}$], where $\vec{n}_1, \vec{n}_2$ are the two normal vectors.

Q: Why does the angle between planes equal the angle between their normals?
A: Rotating both normals by 90° about their common perpendicular yields vectors lying in the respective planes along the line of steepest tilt. Angle is preserved under this rotation, so the normal-angle equals the plane-angle (dihedral angle).

Q: Why do we take the absolute value of $\vec{n}_1 \cdot \vec{n}_2$ when computing the angle between planes?
A: Each plane has two opposite normal directions. Flipping one normal flips the sign of the dot product but the plane-pair is unchanged, so we report the acute angle via $|\vec{n}_1 \cdot \vec{n}_2|$.

C: Two planes are perpendicular iff [$\vec{n}_1 \cdot \vec{n}_2 = 0$], and parallel iff their normals are scalar multiples.

## 2.14 Line of Intersection of Two Planes

Q: What is the direction vector of the line formed by the intersection of two non-parallel planes?
A: It is $\vec{v} = \vec{n}_1 \times \vec{n}_2$, the cross product of the two plane normals. The intersection line lies in both planes, so it is perpendicular to both normals — exactly what the cross product produces.

P: How do you find parametric equations for the line of intersection of two non-parallel planes?

S:
**IDENTIFY**: Intersection of two planes, each given by a scalar equation.

**PLAN**:
- Find direction: $\vec{v} = \vec{n}_1 \times \vec{n}_2$.
- Find one point on both planes by fixing one variable (e.g., set $z = 0$) and solving the resulting 2×2 system.
- Write parametric equations using the point and direction.

**EXECUTE**:
1. Read off $\vec{n}_1$ and $\vec{n}_2$ from the coefficients in each plane equation.
2. Compute $\vec{v} = \vec{n}_1 \times \vec{n}_2 = \langle a, b, c\rangle$.
3. Set $z = 0$ (or whichever variable simplifies), reducing to two equations in $x, y$; solve for a specific point $(x_0, y_0, 0)$.
4. Write $x = x_0 + at$, $y = y_0 + bt$, $z = ct$.

**EVALUATE**:
- Substitute the parametric expressions into both original plane equations to confirm they hold for all $t$.
- If $\vec{n}_1 \times \vec{n}_2 = \vec{0}$, the planes are parallel (no intersection or coincident).

## 2.15 Traces of a Surface

C: A [trace] of a surface is its intersection with a plane, most commonly one of the coordinate planes ($xy$, $yz$, or $xz$) or a plane parallel to them.

Q: Why are traces useful for visualizing 3D surfaces?
A: A surface is 2D inside 3D and hard to picture directly. Traces reduce it to familiar 2D curves (ellipses, parabolas, hyperbolas, lines) that we can sketch, and stacking these cross-sections reveals the full shape.

Q: How do you compute the trace of a surface in the plane $z = k$?
A: Substitute $z = k$ into the surface equation; the resulting equation in $x$ and $y$ describes a curve in that horizontal plane. Repeating for several $k$ values shows how the cross-section evolves with height.

## 2.16 Ellipsoid

C: The standard ellipsoid centered at the origin has equation [$\dfrac{x^2}{a^2} + \dfrac{y^2}{b^2} + \dfrac{z^2}{c^2} = 1$], where $a, b, c > 0$ are the semi-axis lengths along $x$, $y$, $z$.

Q: What do the three coordinate-plane traces of the ellipsoid $\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$ look like?
A: Each trace is an ellipse: in $z=0$ we get $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$; in $y=0$, $\frac{x^2}{a^2} + \frac{z^2}{c^2} = 1$; in $x=0$, $\frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$. All three are bounded, confirming the surface is closed.

Q: When does an ellipsoid become a sphere?
A: When $a = b = c = R$, the equation becomes $x^2 + y^2 + z^2 = R^2$, a sphere of radius $R$. Spheres are the rotationally symmetric special case of ellipsoids.

## 2.17 Elliptic Paraboloid

C: The standard elliptic paraboloid opening upward has equation [$z = \dfrac{x^2}{a^2} + \dfrac{y^2}{b^2}$], where $a, b > 0$ control the widths of its elliptical cross-sections.

Q: What shapes are the horizontal ($z = k$) and vertical traces of $z = \frac{x^2}{a^2} + \frac{y^2}{b^2}$?
A: Horizontal traces $z = k$: ellipses for $k > 0$, a single point at $k = 0$, empty for $k < 0$. Vertical traces (e.g., $y = 0$) are parabolas: $z = x^2/a^2$. Hence the name elliptic paraboloid.

Q: Why is $z = x^2 + y^2$ bowl-shaped rather than saddle-shaped?
A: Both squared terms have the same sign, so $z \ge 0$ and $z$ grows in every horizontal direction away from the origin. The surface has a single minimum at the origin and curves upward everywhere, forming a bowl.

## 2.18 Hyperbolic Paraboloid (Saddle)

C: The hyperbolic paraboloid has equation [$z = \dfrac{x^2}{a^2} - \dfrac{y^2}{b^2}$], characterized by the opposite signs of the two squared terms.

Q: Why is the surface $z = \frac{x^2}{a^2} - \frac{y^2}{b^2}$ called a saddle?
A: Along the $x$-axis ($y=0$) it curves upward ($z = x^2/a^2$), while along the $y$-axis ($x=0$) it curves downward ($z = -y^2/b^2$). The origin is a minimum in one direction and a maximum in another — the defining feature of a saddle point.

Q: What do the horizontal traces $z = k$ of a hyperbolic paraboloid look like?
A: For $k \neq 0$, $\frac{x^2}{a^2} - \frac{y^2}{b^2} = k$ is a hyperbola. The orientation of the hyperbola flips when $k$ changes sign. For $k = 0$, it degenerates into the two lines $y = \pm (b/a)x$.

## 2.19 Cone

C: The standard elliptic cone with apex at the origin has equation [$z^2 = \dfrac{x^2}{a^2} + \dfrac{y^2}{b^2}$], consisting of two nappes meeting at the origin.

Q: Why does $z^2 = x^2 + y^2$ describe a double cone rather than just an upward cone?
A: Squaring allows both signs: $z = +\sqrt{x^2+y^2}$ is the upper nappe, $z = -\sqrt{x^2+y^2}$ is the lower nappe. Both satisfy $z^2 = x^2 + y^2$, so the full surface is a two-nappe cone meeting at the origin.

Q: What happens to a cone's horizontal traces as $|z|$ increases?
A: They are ellipses $\frac{x^2}{a^2} + \frac{y^2}{b^2} = z^2$, whose semi-axes grow linearly with $|z|$. That linear growth (rather than parabolic) is what distinguishes a cone from a paraboloid.

## 2.20 Hyperboloids of One vs. Two Sheets

C: The hyperboloid of [one sheet] has equation $\dfrac{x^2}{a^2} + \dfrac{y^2}{b^2} - \dfrac{z^2}{c^2} = 1$ (one minus sign), forming a single connected "hourglass with a waist".

C: The hyperboloid of [two sheets] has equation $-\dfrac{x^2}{a^2} - \dfrac{y^2}{b^2} + \dfrac{z^2}{c^2} = 1$ (two minus signs), forming two disconnected bowl-like pieces along the axis.

Q: How do you distinguish a hyperboloid of one sheet from two sheets by inspecting the equation?
A: Write it as (sum/difference) $= 1$. One sheet has exactly one negative squared term (connected surface). Two sheets has exactly two negative squared terms (or equivalently one positive term), producing two disconnected pieces along the axis of the positive term.

Q: How do horizontal traces differ between hyperboloids of one and two sheets?
A: One sheet: horizontal traces are ellipses for all $z$ (always a cross-section exists, smallest at the waist $z=0$). Two sheets: horizontal traces are empty for $|z| < c$ and become ellipses only when $|z| \ge c$ — the gap between the two pieces.

Q: What is the asymptotic surface shared by a hyperboloid of one or two sheets?
A: Both approach the cone $\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 0$ as $|z| \to \infty$. The constant $1$ on the right shifts the cone into a hyperboloid; the sign pattern determines which type.

## 2.21 Cylindrical Coordinates

C: Cylindrical coordinates $(r, \theta, z)$ describe a point by its polar coordinates $(r, \theta)$ in the $xy$-plane plus the same [$z$] as in Cartesian coordinates, where $r \ge 0$ and $\theta$ is measured from the positive $x$-axis.

C: Conversion from cylindrical $(r, \theta, z)$ to Cartesian $(x, y, z)$: [$x = r\cos\theta$], $y = r\sin\theta$, and $z = z$.

C: Conversion from Cartesian $(x, y, z)$ to cylindrical: [$r = \sqrt{x^2 + y^2}$], $\theta = \operatorname{atan2}(y, x)$, and $z = z$.

Q: When are cylindrical coordinates more convenient than Cartesian?
A: When a problem has rotational symmetry about the $z$-axis — e.g., cylinders, cones, paraboloids, or solids of revolution. The symmetry makes $\theta$ absent (or separable), simplifying equations and integrals.

Q: What does the equation $r = 2$ describe in cylindrical coordinates?
A: A cylinder of radius 2 centered on the $z$-axis, because $\theta$ and $z$ are free. In Cartesian form this is $x^2 + y^2 = 4$, independent of $z$.

## 2.22 Spherical Coordinates

C: Spherical coordinates $(\rho, \theta, \phi)$ describe a point by its distance [$\rho$] from the origin, the azimuthal angle $\theta$ (from the positive $x$-axis in the $xy$-plane), and the polar angle $\phi$ measured from the positive $z$-axis, with $\rho \ge 0$ and $0 \le \phi \le \pi$.

C: Conversion from spherical $(\rho, \theta, \phi)$ to Cartesian: [$x = \rho\sin\phi\cos\theta$], $y = \rho\sin\phi\sin\theta$, and $z = \rho\cos\phi$.

C: Conversion from Cartesian $(x, y, z)$ to spherical: [$\rho = \sqrt{x^2 + y^2 + z^2}$], $\phi = \arccos(z/\rho)$, and $\theta = \operatorname{atan2}(y, x)$.

Q: Why does $z = \rho\cos\phi$ in spherical coordinates, while $x$ and $y$ both carry a factor of $\sin\phi$?
A: $\phi$ is measured from the $z$-axis, so the component along $z$ is $\rho\cos\phi$ (adjacent). The projection onto the $xy$-plane has length $\rho\sin\phi$ (opposite), which is then split into $x$ and $y$ by the azimuthal angle $\theta$.

Q: When are spherical coordinates more convenient than cylindrical?
A: When a problem has full spherical symmetry about the origin — e.g., spheres, gravitational or electric fields from a point source, or integrals over ball-shaped regions. Then $\rho$ alone captures the radial dependence.

Q: What does the equation $\phi = \pi/4$ describe in spherical coordinates?
A: A cone opening upward from the origin with a half-angle of $45°$ about the $z$-axis. Every point making a fixed angle $\phi$ with the positive $z$-axis lies on such a cone.

## 2.23 Plane Through Three Points (Worked Problem)

P: Find the equation of the plane containing the points $A = (1, 0, 1)$, $B = (2, -1, 3)$, and $C = (0, 1, -1)$.

S:
**IDENTIFY**: Plane from three non-collinear points — use two in-plane vectors and their cross product to get a normal.

**PLAN**:
- Form $\vec{u} = \vec{AB}$ and $\vec{v} = \vec{AC}$.
- Compute $\vec{n} = \vec{u} \times \vec{v}$.
- Use point-normal equation with anchor $A$.

**EXECUTE**:
1. $\vec{u} = B - A = \langle 2-1,\; -1-0,\; 3-1\rangle = \langle 1, -1, 2\rangle$.
2. $\vec{v} = C - A = \langle 0-1,\; 1-0,\; -1-1\rangle = \langle -1, 1, -2\rangle$.
3. $\vec{n} = \vec{u} \times \vec{v} = \langle (-1)(-2) - (2)(1),\; (2)(-1) - (1)(-2),\; (1)(1) - (-1)(-1)\rangle = \langle 0, 0, 0\rangle$.
4. Since $\vec{n} = \vec{0}$, $\vec{u}$ and $\vec{v}$ are parallel — indeed $\vec{v} = -\vec{u}$ — so the three points are collinear.

**EVALUATE**:
- Check: $B - A = \langle 1,-1,2\rangle$ and $C - A = \langle -1,1,-2\rangle = -(B-A)$, confirming $A$, $B$, $C$ lie on a single line.
- Therefore no unique plane contains them; infinitely many planes pass through this line.
- Lesson: always check $\vec{n} \neq \vec{0}$ before writing the plane equation.

## 2.24 Line of Intersection of Two Planes (Worked Problem)

P: Find parametric equations for the line of intersection of the planes $x + y + z = 1$ and $x - y + 2z = 0$.

S:
**IDENTIFY**: Intersection of two non-parallel planes — direction from cross product of normals, point from solving the system with one variable fixed.

**PLAN**:
- Extract normals $\vec{n}_1 = \langle 1,1,1\rangle$ and $\vec{n}_2 = \langle 1,-1,2\rangle$.
- Direction $\vec{v} = \vec{n}_1 \times \vec{n}_2$.
- Set $z = 0$ and solve for a particular point.

**EXECUTE**:
1. $\vec{v} = \vec{n}_1 \times \vec{n}_2 = \langle (1)(2) - (1)(-1),\; (1)(1) - (1)(2),\; (1)(-1) - (1)(1)\rangle = \langle 3, -1, -2\rangle$.
2. Set $z = 0$: system becomes $x + y = 1$ and $x - y = 0$, giving $x = y = 1/2$.
3. Particular point: $(1/2,\; 1/2,\; 0)$.
4. Parametric equations: $x = \tfrac{1}{2} + 3t$, $y = \tfrac{1}{2} - t$, $z = -2t$.

**EVALUATE**:
- Check plane 1: $x+y+z = \tfrac{1}{2}+3t + \tfrac{1}{2}-t + (-2t) = 1 + 0\cdot t = 1$. ✓
- Check plane 2: $x-y+2z = (\tfrac{1}{2}+3t) - (\tfrac{1}{2}-t) + 2(-2t) = 4t - 4t = 0$. ✓
- Both hold for all $t$, confirming the parametrization traces the entire intersection line.
