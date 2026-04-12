+++
order = 1
subject = "Math"
tags = ["math", "multivariable-calculus", "vectors", "3d-geometry", "dot-product", "cross-product"]
+++

# Multivariable Calculus — Vectors and the Geometry of 3-Space

## 1.1 Why Multivariable Calculus Starts with Vectors and 3D Geometry

Q: Why does multivariable calculus begin with vectors and 3D geometry rather than diving straight into partial derivatives?
A: The objects of study in multivariable calculus — curves, surfaces, vector fields — all live in $\mathbb{R}^2$ and $\mathbb{R}^3$ (or higher). To differentiate and integrate over them, we first need a language for describing points, directions, and displacements in space. Vectors provide that language: they encode magnitude and direction independently of any origin, and they let us express geometric ideas (lines, planes, tangents, normals) as algebraic equations that calculus can operate on.

Q: Why are directions fundamentally more important in multivariable calculus than in single-variable calculus?
A: In one dimension there are only two directions (left and right), so a derivative is just a single number — the slope. In $\mathbb{R}^2$ or $\mathbb{R}^3$ you can approach a point from infinitely many directions, and the rate of change generally depends on which direction you take. Vectors let us specify, compare, and compute along these directions, which is essential for partial derivatives, directional derivatives, and gradients.

C: The natural setting for multivariable calculus is [$\mathbb{R}^3$], the set of ordered triples $(x, y, z)$ of real numbers.

## 1.2 3D Coordinate System, Right-Hand Rule, and Octants

Q: How is a 3D rectangular coordinate system set up, and why must we fix an orientation?
A: Choose an origin $O$ and three mutually perpendicular axes, labeled $x$, $y$, $z$. Each point is specified by an ordered triple $(x, y, z)$ giving its signed distance along each axis. We must fix an orientation because cross products and oriented surfaces depend on whether the system is right-handed or left-handed — the same computation produces opposite-sign answers in a mirrored frame.

Q: What is the right-hand rule for orienting the 3D axes?
A: Point the fingers of your right hand along the positive $x$-axis and curl them toward the positive $y$-axis; your thumb then points along the positive $z$-axis. Equivalently, $\vec{i} \times \vec{j} = \vec{k}$. This convention is used throughout physics and multivariable calculus so that cross products, curls, and surface normals have consistent signs.

C: A [right-handed] coordinate system is one where curling the fingers of the right hand from the positive $x$-axis to the positive $y$-axis makes the thumb point along the positive $z$-axis.

Q: What is an octant, and how many are there in $\mathbb{R}^3$?
A: An octant is one of the eight regions into which the three coordinate planes ($xy$, $xz$, $yz$) divide $\mathbb{R}^3$. Each octant is characterized by the signs of $x$, $y$, $z$ (e.g., $(+,+,+)$ is the first octant). There are $2^3 = 8$ octants because each of the three coordinates can independently be positive or negative.

C: The [first octant] of $\mathbb{R}^3$ is the region where $x > 0$, $y > 0$, and $z > 0$.

## 1.3 Distance Formula in $\mathbb{R}^3$

Q: Why does the 3D distance formula contain a square root of a sum of three squared differences?
A: Between two points $P_1 = (x_1, y_1, z_1)$ and $P_2 = (x_2, y_2, z_2)$, apply the Pythagorean theorem twice: first in the $xy$-plane to get the horizontal leg $\sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$, then combine that leg with the vertical leg $|z_2 - z_1|$ in a right triangle. The result is the straight-line Euclidean distance, which extends the 2D formula by adding a third squared term.

C: The distance between $P_1 = (x_1, y_1, z_1)$ and $P_2 = (x_2, y_2, z_2)$ in $\mathbb{R}^3$ is $d = [\sqrt{(x_2-x_1)^2 + (y_2-y_1)^2 + (z_2-z_1)^2}]$, where each squared term measures the separation along one coordinate axis.

Q: What does the distance formula reduce to if the two points share the same $z$-coordinate, and why?
A: It reduces to the familiar 2D distance formula $d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$ because $z_2 - z_1 = 0$, so the third squared term vanishes. Geometrically, the two points lie in a horizontal plane and their separation is purely planar.

## 1.4 Equation of a Sphere

Q: Why is the equation of a sphere of radius $r$ centered at $(h, k, l)$ given by $(x-h)^2 + (y-k)^2 + (z-l)^2 = r^2$?
A: A sphere is defined as the set of all points at a fixed distance $r$ from its center. Apply the 3D distance formula from $(h, k, l)$ to a generic point $(x, y, z)$ and set it equal to $r$; squaring both sides gives the stated equation. The squared form avoids the square root and is a cleaner algebraic object to manipulate.

C: A sphere of radius $r$ centered at $(h, k, l)$ satisfies $[(x-h)^2 + (y-k)^2 + (z-l)^2 = r^2]$, where $(x, y, z)$ is any point on the sphere.

Q: How do you find the center and radius of a sphere given an equation like $x^2 + y^2 + z^2 - 4x + 6y - 2z = 11$?
A: Complete the square in each variable to rewrite it in standard form. Here: $(x-2)^2 - 4 + (y+3)^2 - 9 + (z-1)^2 - 1 = 11$, giving $(x-2)^2 + (y+3)^2 + (z-1)^2 = 25$. So the center is $(2, -3, 1)$ and the radius is $r = 5$.

## 1.5 Vectors vs Points — Magnitude and Direction, No Fixed Location

Q: What is the key conceptual difference between a point and a vector in $\mathbb{R}^3$?
A: A point specifies a fixed location in space. A vector specifies a displacement — a magnitude and a direction — with no fixed location: the same vector can be drawn starting from any tail point. Two vectors are equal if and only if they have the same length and same direction, regardless of where they are placed.

C: A vector is characterized only by its [magnitude and direction], not by its location in space.

Q: Why is it useful that vectors have no fixed starting point?
A: Because displacements, velocities, forces, and other physical quantities act "the same way" regardless of where they are applied. Free vectors can be translated parallel to themselves without changing identity, which makes vector arithmetic (addition, scaling, dot/cross products) independent of where you draw the arrows — a huge algebraic simplification.

## 1.6 Component Form and Standard Unit Vectors

Q: What does it mean to write a vector in component form $\vec{v} = \langle a, b, c \rangle$?
A: It means $\vec{v}$ represents a displacement of $a$ units along the $x$-axis, $b$ units along the $y$-axis, and $c$ units along the $z$-axis. Equivalently, if $\vec{v}$ is drawn with its tail at the origin, its head sits at the point $(a, b, c)$. The angle brackets distinguish the vector from the point.

C: In component form, a vector in $\mathbb{R}^3$ is written as $\vec{v} = \langle [a, b, c] \rangle$, where $a$, $b$, and $c$ are its components along the $x$-, $y$-, and $z$-axes respectively.

Q: What are the standard unit vectors $\vec{i}$, $\vec{j}$, $\vec{k}$, and why are they useful?
A: They are the unit vectors along the positive coordinate axes: $\vec{i} = \langle 1, 0, 0 \rangle$, $\vec{j} = \langle 0, 1, 0 \rangle$, $\vec{k} = \langle 0, 0, 1 \rangle$. Any vector in $\mathbb{R}^3$ can be uniquely written as $\vec{v} = a\vec{i} + b\vec{j} + c\vec{k}$, which makes them an orthonormal basis and simplifies both algebraic manipulation and geometric interpretation.

C: The standard unit vectors in $\mathbb{R}^3$ are $\vec{i} = \langle 1, 0, 0 \rangle$, $\vec{j} = \langle 0, 1, 0 \rangle$, and $[\vec{k} = \langle 0, 0, 1 \rangle]$.

## 1.7 Vector Addition and Scalar Multiplication

Q: How do you add two vectors in component form, and what does it mean geometrically?
A: Add them component-wise: $\langle a_1, b_1, c_1 \rangle + \langle a_2, b_2, c_2 \rangle = \langle a_1+a_2, b_1+b_2, c_1+c_2 \rangle$, where the subscripts label the two vectors. Geometrically this is the "tip-to-tail" rule or parallelogram rule: place the tail of the second vector at the head of the first; the sum runs from the original tail to the final head.

C: Vector addition is performed [component-wise]: $\langle a_1, b_1, c_1 \rangle + \langle a_2, b_2, c_2 \rangle = \langle a_1+a_2, b_1+b_2, c_1+c_2 \rangle$.

Q: What does scalar multiplication $k\vec{v}$ do geometrically, and how is it computed?
A: It multiplies each component of $\vec{v}$ by the scalar $k$: if $\vec{v} = \langle a, b, c \rangle$, then $k\vec{v} = \langle ka, kb, kc \rangle$. Geometrically, $|k|$ rescales the length by a factor of $|k|$; if $k > 0$ the direction is preserved, if $k < 0$ the vector is reversed, and if $k = 0$ the result is the zero vector.

C: Scalar multiplication is component-wise: $k\langle a, b, c \rangle = [\langle ka, kb, kc \rangle]$, where $k$ is a real scalar.

## 1.8 Magnitude (Norm) of a Vector

Q: Why does the magnitude of $\vec{v} = \langle a, b, c \rangle$ equal $\sqrt{a^2 + b^2 + c^2}$?
A: If you draw $\vec{v}$ with its tail at the origin, its head sits at the point $(a, b, c)$. The length of $\vec{v}$ is the distance from the origin to that point, which by the 3D distance formula is $\sqrt{a^2 + b^2 + c^2}$. So the magnitude is just the Euclidean length of the displacement arrow.

C: The magnitude (norm) of $\vec{v} = \langle a, b, c \rangle$ is $|\vec{v}| = [\sqrt{a^2 + b^2 + c^2}]$, where $a$, $b$, $c$ are its components.

Q: What does it mean for a vector to have magnitude zero?
A: It means $a = b = c = 0$, so the vector is the zero vector $\vec{0} = \langle 0, 0, 0 \rangle$. The zero vector has no well-defined direction, which is why results like "two vectors are parallel iff their cross product is zero" have to treat the zero vector as a special case.

## 1.9 Unit Vectors

Q: Why does dividing a vector by its magnitude produce a unit vector?
A: If $\vec{v} \neq \vec{0}$, then $\hat{v} = \vec{v}/|\vec{v}|$ is a scalar multiple of $\vec{v}$ (scalar $= 1/|\vec{v}|$), so it points in the same direction. Its magnitude is $|\vec{v}|/|\vec{v}| = 1$, so it has unit length. The operation strips away the magnitude information while preserving direction.

C: The unit vector in the direction of $\vec{v} \neq \vec{0}$ is $\hat{v} = [\vec{v}/|\vec{v}|]$, where $|\vec{v}|$ is the magnitude of $\vec{v}$.

Q: Why is normalizing a vector to unit length so useful in practice?
A: Unit vectors encode pure direction with no magnitude baggage, which is what we want when we ask "how much of quantity $X$ points in direction $\hat{v}$?" For example, directional derivatives, projections, and surface normals are all most naturally expressed using unit vectors so that scaling effects are separated from directional effects.

## 1.10 Dot Product — Algebraic Definition

Q: How is the dot product of two vectors defined algebraically in component form?
A: For $\vec{u} = \langle u_1, u_2, u_3 \rangle$ and $\vec{v} = \langle v_1, v_2, v_3 \rangle$, the dot product is $\vec{u} \cdot \vec{v} = u_1 v_1 + u_2 v_2 + u_3 v_3$, a single real number (a scalar). It is commutative ($\vec{u} \cdot \vec{v} = \vec{v} \cdot \vec{u}$) and distributes over vector addition.

C: The dot product in $\mathbb{R}^3$ is $\vec{u} \cdot \vec{v} = [u_1 v_1 + u_2 v_2 + u_3 v_3]$, where $u_i$ and $v_i$ are the $i$-th components of $\vec{u}$ and $\vec{v}$.

Q: Why is the dot product called a "scalar product"?
A: Because it takes two vectors as input and returns a scalar (a single real number) as output, unlike the cross product which returns a vector. The scalar output typically encodes how much the two vectors align — positive if they roughly agree in direction, zero if perpendicular, negative if roughly opposite.

## 1.11 Dot Product — Geometric Formula

Q: Before seeing the proof: predict what $\vec{u} \cdot \vec{v}$ should equal when $\vec{u}$ and $\vec{v}$ point in exactly the same direction.
A: Predict: it should equal $|\vec{u}||\vec{v}|$, because the angle between them is $0$ and $\cos 0 = 1$. More generally you would expect the dot product to depend on both magnitudes and on some measure of alignment — $\cos\theta$ is the natural candidate.

Q: What is the geometric formula for the dot product, and what does each symbol mean?
A: $\vec{u} \cdot \vec{v} = |\vec{u}| |\vec{v}| \cos\theta$, where $|\vec{u}|$ and $|\vec{v}|$ are the magnitudes of $\vec{u}$ and $\vec{v}$, and $\theta \in [0, \pi]$ is the angle between them when placed tail-to-tail. This follows from the algebraic definition via the law of cosines.

C: The geometric form of the dot product is $\vec{u} \cdot \vec{v} = [|\vec{u}||\vec{v}|\cos\theta]$, where $\theta$ is the angle between $\vec{u}$ and $\vec{v}$ placed tail-to-tail.

Q: Why is the geometric formula more useful than the algebraic one for proving theorems?
A: Because it reveals that the dot product is intrinsically geometric — independent of coordinates. Any orthogonal change of basis leaves magnitudes and the angle between vectors unchanged, so it leaves the dot product unchanged. This invariance is what lets the dot product detect angles, orthogonality, and projections coordinate-free.

## 1.12 Finding the Angle Between Vectors

Q: How do you find the angle between two nonzero vectors $\vec{u}$ and $\vec{v}$?
A: Solve the geometric formula for $\cos\theta$: $\cos\theta = \frac{\vec{u} \cdot \vec{v}}{|\vec{u}||\vec{v}|}$, then take $\theta = \arccos\!\left(\frac{\vec{u} \cdot \vec{v}}{|\vec{u}||\vec{v}|}\right)$, which yields $\theta \in [0, \pi]$. Compute the dot product via components and the magnitudes via $\sqrt{a^2+b^2+c^2}$.

C: The angle $\theta$ between nonzero $\vec{u}$ and $\vec{v}$ satisfies $\cos\theta = [\frac{\vec{u} \cdot \vec{v}}{|\vec{u}||\vec{v}|}]$, where $|\vec{u}|, |\vec{v}|$ are the magnitudes.

## 1.13 Orthogonality

Q: Why are two nonzero vectors orthogonal if and only if their dot product is zero?
A: From the geometric formula, $\vec{u} \cdot \vec{v} = |\vec{u}||\vec{v}|\cos\theta$. With $|\vec{u}|, |\vec{v}| > 0$, this is zero iff $\cos\theta = 0$, i.e., $\theta = \pi/2$. So a zero dot product is exactly the condition that the vectors meet at a right angle.

C: Two nonzero vectors $\vec{u}$ and $\vec{v}$ are orthogonal ($\vec{u} \perp \vec{v}$) iff $[\vec{u} \cdot \vec{v} = 0]$.

Q: Why is the zero vector considered orthogonal to every vector by convention?
A: Because the equation $\vec{0} \cdot \vec{v} = 0$ holds for any $\vec{v}$. Treating the zero vector as orthogonal to everything keeps statements like "orthogonal complements are subspaces" clean, even though $\vec{0}$ has no well-defined direction or angle.

## 1.14 Scalar and Vector Projections

Q: What does the scalar projection of $\vec{u}$ onto $\vec{v}$ measure, and how is it computed?
A: It measures the signed length of the "shadow" of $\vec{u}$ along the direction of $\vec{v}$: how much of $\vec{u}$ lies in the direction of $\vec{v}$. It equals $\text{comp}_{\vec{v}} \vec{u} = \frac{\vec{u} \cdot \vec{v}}{|\vec{v}|} = |\vec{u}|\cos\theta$, where $\theta$ is the angle between the vectors. The sign is negative when $\vec{u}$ leans away from $\vec{v}$ (obtuse angle).

Q: What is the vector projection of $\vec{u}$ onto $\vec{v}$, and how is it constructed from the scalar projection?
A: It is the vector along $\vec{v}$ whose length is the scalar projection: $\text{proj}_{\vec{v}} \vec{u} = \left(\frac{\vec{u} \cdot \vec{v}}{|\vec{v}|}\right)\hat{v} = \frac{\vec{u} \cdot \vec{v}}{|\vec{v}|^2}\vec{v}$, where $\hat{v} = \vec{v}/|\vec{v}|$ is the unit vector along $\vec{v}$. The second form avoids computing $|\vec{v}|$ separately.

C: The vector projection of $\vec{u}$ onto $\vec{v}$ is $\text{proj}_{\vec{v}} \vec{u} = [\frac{\vec{u} \cdot \vec{v}}{|\vec{v}|^2}\vec{v}]$, where $\vec{v}$ is the nonzero vector being projected onto.

Q: Why is vector projection useful in multivariable calculus?
A: It decomposes any vector $\vec{u}$ into a component along $\vec{v}$ ($\text{proj}_{\vec{v}} \vec{u}$) plus a component orthogonal to $\vec{v}$ ($\vec{u} - \text{proj}_{\vec{v}} \vec{u}$). This decomposition underlies tangential vs normal components of force, work ($W = \vec{F} \cdot \vec{d}$), and orthogonal decompositions used throughout calculus and linear algebra.

## 1.15 Cross Product — Determinant Formula

Q: How is the cross product $\vec{u} \times \vec{v}$ computed using a determinant?
A: Write a symbolic $3 \times 3$ determinant with $\vec{i}, \vec{j}, \vec{k}$ in the first row, the components of $\vec{u}$ in the second, and those of $\vec{v}$ in the third: $\vec{u} \times \vec{v} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{vmatrix}$. Expanding along the first row gives $\vec{u} \times \vec{v} = \langle u_2 v_3 - u_3 v_2,\ u_3 v_1 - u_1 v_3,\ u_1 v_2 - u_2 v_1 \rangle$.

C: The cross product components are $\vec{u} \times \vec{v} = \langle [u_2 v_3 - u_3 v_2,\ u_3 v_1 - u_1 v_3,\ u_1 v_2 - u_2 v_1] \rangle$, where $u_i, v_i$ are the components of $\vec{u}, \vec{v}$.

Q: Why does the cross product return a vector, unlike the dot product?
A: The cross product is designed to produce the directed normal to the plane spanned by $\vec{u}$ and $\vec{v}$, with magnitude encoding the parallelogram area. Direction is intrinsic information in 3D geometry (think surface orientation, torque, angular velocity), so the output must be a vector, not a scalar.

## 1.16 Geometric Properties of the Cross Product

Q: What two geometric facts completely characterize $\vec{u} \times \vec{v}$?
A: (1) Its direction is perpendicular to both $\vec{u}$ and $\vec{v}$, oriented by the right-hand rule (curl right-hand fingers from $\vec{u}$ toward $\vec{v}$; thumb points along $\vec{u} \times \vec{v}$). (2) Its magnitude is $|\vec{u} \times \vec{v}| = |\vec{u}||\vec{v}|\sin\theta$, where $\theta \in [0, \pi]$ is the angle between the vectors.

C: The magnitude of the cross product satisfies $|\vec{u} \times \vec{v}| = [|\vec{u}||\vec{v}|\sin\theta]$, where $\theta$ is the angle between $\vec{u}$ and $\vec{v}$.

Q: Why is $\vec{u} \times \vec{v} = \vec{0}$ if and only if $\vec{u}$ and $\vec{v}$ are parallel (or one is zero)?
A: From $|\vec{u} \times \vec{v}| = |\vec{u}||\vec{v}|\sin\theta$, the magnitude vanishes iff $|\vec{u}| = 0$, $|\vec{v}| = 0$, or $\sin\theta = 0$ (i.e., $\theta = 0$ or $\pi$). The last case is exactly the parallel (or anti-parallel) condition. This gives a quick algebraic parallelism test.

## 1.17 Cross Product and Parallelogram Area

Q: Why does $|\vec{u} \times \vec{v}|$ equal the area of the parallelogram spanned by $\vec{u}$ and $\vec{v}$?
A: The parallelogram with sides $\vec{u}$ and $\vec{v}$ has base $|\vec{u}|$ and height $|\vec{v}|\sin\theta$ (perpendicular height from the tip of $\vec{v}$ to the line of $\vec{u}$), where $\theta$ is the angle between them. So area $= \text{base} \times \text{height} = |\vec{u}||\vec{v}|\sin\theta = |\vec{u} \times \vec{v}|$. Halving gives the area of the triangle with the same two sides.

C: The area of the parallelogram spanned by $\vec{u}$ and $\vec{v}$ equals $[|\vec{u} \times \vec{v}|]$, where $\vec{u}, \vec{v}$ are the adjacent-side vectors.

## 1.18 Anti-Commutativity of the Cross Product

Q: Why does swapping the order of a cross product flip its sign: $\vec{u} \times \vec{v} = -\vec{v} \times \vec{u}$?
A: Algebraically, swapping the last two rows of the $3 \times 3$ determinant definition multiplies the determinant by $-1$. Geometrically, swapping the factors reverses the right-hand-rule direction: the perpendicular now points to the opposite side of the plane spanned by the two vectors, while the magnitude (parallelogram area) is unchanged.

C: The cross product is anti-commutative: $\vec{u} \times \vec{v} = [-\vec{v} \times \vec{u}]$.

Q: What immediate consequence does anti-commutativity have for $\vec{v} \times \vec{v}$?
A: Setting $\vec{u} = \vec{v}$ gives $\vec{v} \times \vec{v} = -\vec{v} \times \vec{v}$, so $2(\vec{v} \times \vec{v}) = \vec{0}$ and thus $\vec{v} \times \vec{v} = \vec{0}$. Any vector crossed with itself is zero — consistent with the fact that it is parallel to itself.

## 1.19 Scalar Triple Product and Parallelepiped Volume

Q: What is the scalar triple product $\vec{u} \cdot (\vec{v} \times \vec{w})$, and what does it compute geometrically?
A: It is a scalar equal to the signed volume of the parallelepiped with edges $\vec{u}$, $\vec{v}$, $\vec{w}$ emanating from a common vertex. In absolute value, $V = |\vec{u} \cdot (\vec{v} \times \vec{w})|$: the base parallelogram has area $|\vec{v} \times \vec{w}|$ and $\vec{u} \cdot \hat{n}$ gives the signed height along the base's normal $\hat{n}$, so the dot product multiplies base area by signed height.

C: The volume of the parallelepiped with edges $\vec{u}, \vec{v}, \vec{w}$ is $V = [|\vec{u} \cdot (\vec{v} \times \vec{w})|]$, the absolute value of the scalar triple product.

Q: Why does $\vec{u} \cdot (\vec{v} \times \vec{w}) = 0$ tell you the three vectors are coplanar?
A: Zero signed volume means the parallelepiped is degenerate — it has been flattened. This happens exactly when the three edge vectors lie in a common plane, i.e., they are linearly dependent. So the scalar triple product is a clean test for coplanarity of three vectors in $\mathbb{R}^3$.

## 1.20 Worked Example — Angle Between Vectors

P: Find the angle between $\vec{u} = \langle 1, 2, 3 \rangle$ and $\vec{v} = \langle -1, 0, 2 \rangle$.

S:
**IDENTIFY**: Angle-between-vectors problem in $\mathbb{R}^3$. Use the dot-product relation $\cos\theta = (\vec{u} \cdot \vec{v})/(|\vec{u}||\vec{v}|)$, where $\theta \in [0, \pi]$.

**PLAN**:
- Compute the dot product $\vec{u} \cdot \vec{v}$ component-wise.
- Compute magnitudes $|\vec{u}|$ and $|\vec{v}|$ via $\sqrt{a^2+b^2+c^2}$.
- Divide to get $\cos\theta$, then take $\arccos$.

**EXECUTE**:
1. Dot product: $\vec{u} \cdot \vec{v} = (1)(-1) + (2)(0) + (3)(2) = -1 + 0 + 6 = 5$.
2. Magnitudes: $|\vec{u}| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{14}$ and $|\vec{v}| = \sqrt{(-1)^2 + 0^2 + 2^2} = \sqrt{5}$.
3. Cosine: $\cos\theta = \frac{5}{\sqrt{14}\sqrt{5}} = \frac{5}{\sqrt{70}}$.
4. Angle: $\theta = \arccos\!\left(\frac{5}{\sqrt{70}}\right) \approx \arccos(0.5976) \approx 0.9303\ \text{rad} \approx 53.3^\circ$.

**EVALUATE**: The dot product is positive, so $\theta$ must be acute ($< 90^\circ$) — consistent with $53.3^\circ$. Also $|\cos\theta| = 5/\sqrt{70} \approx 0.60 \le 1$, so the Cauchy–Schwarz inequality is satisfied, confirming the arithmetic.

## 1.21 Worked Example — Orthogonal Vector and Parallelogram Area

P: Find a vector orthogonal to both $\vec{a} = \langle 1, 1, 0 \rangle$ and $\vec{b} = \langle 0, 1, 1 \rangle$, and compute the area of the parallelogram they span.

S:
**IDENTIFY**: Cross-product problem. $\vec{a} \times \vec{b}$ is orthogonal to both, and $|\vec{a} \times \vec{b}|$ is the parallelogram area.

**PLAN**:
- Compute $\vec{a} \times \vec{b}$ via the determinant formula.
- Take its magnitude with $\sqrt{a^2+b^2+c^2}$ for the area.

**EXECUTE**:
1. Set up the determinant:
$$\vec{a} \times \vec{b} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{vmatrix}.$$
2. Expand along the first row:
   - $\vec{i}$-component: $(1)(1) - (0)(1) = 1$.
   - $\vec{j}$-component: $-[(1)(1) - (0)(0)] = -1$.
   - $\vec{k}$-component: $(1)(1) - (1)(0) = 1$.
   So $\vec{a} \times \vec{b} = \langle 1, -1, 1 \rangle$.
3. Magnitude: $|\vec{a} \times \vec{b}| = \sqrt{1^2 + (-1)^2 + 1^2} = \sqrt{3}$.

**EVALUATE**: Check orthogonality: $\vec{a} \cdot (\vec{a} \times \vec{b}) = (1)(1) + (1)(-1) + (0)(1) = 0$ and $\vec{b} \cdot (\vec{a} \times \vec{b}) = (0)(1) + (1)(-1) + (1)(1) = 0$ — both zero, as required. The area $\sqrt{3} \approx 1.73$ is reasonable: both $\vec{a}$ and $\vec{b}$ have length $\sqrt{2}$ and meet at $60^\circ$ (since $\vec{a} \cdot \vec{b} = 1 = |\vec{a}||\vec{b}|\cos\theta = 2\cos\theta$), giving area $|\vec{a}||\vec{b}|\sin 60^\circ = 2 \cdot \frac{\sqrt{3}}{2} = \sqrt{3}$. ✓
