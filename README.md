[![](https://jitpack.io/v/micycle1/PTS.svg)](https://jitpack.io/#micycle1/PTS) [![Lines of Code](https://sonarcloud.io/api/project_badges/measure?project=micycle1_PTS&metric=ncloc)](https://sonarcloud.io/dashboard?id=micycle1_PTS)

# Processing Topology Suite

<h3 align="center"> 🚧 Under Construction 🚧 </h3>

---
PTS is a library for geometric operations in Processing.

Most methods operate on PShapes, and return PShapes (where applicable).

The library is stateless: methods are static.

A library for shapes in Processing:

- Predicates
  - >Does
- Metrics
  - >What is the area of this polygon?
- Geometric Computation
  - > The union of these two shapes

PTS wraps JTS, enabling its methods to be applied to Processing's `PShape` objects. Beyond that, PTS provides other geometry __ such as splines.

[Contents from https://doc.cgal.org/latest/Manual/packages.html]

## PShapes

- Boolean operations: union, difference, intersection, etc. (/OVERLAY OPERATIONS)
- Shape Boundaries
- Smoothing
- Simplification
- Area, centroid, etc.

### SPATIAL RELATIONSHIPS

- Within
- Contains
###  BUFFERS

### POLYGONIZATION

### Geometry methods
- Spatial Predicates, relate()
- Overlay ops, buffer(), convexHull()
- Metrics

The library is split into a handful of classes as detailed below.

## **Contour**
*Methods to produce a variety of geometric contour lines within shapes.*
### Medial Axis
<img src="resources/contour/medialAxis.png" alt="" width="50%"/>

### Dissolved Medial Axis
A medial axis where small line segments are dissolved into larger, straighter ones.

<img src="resources/contour/medialAxisDissolved.png" alt="" width="50%"/>

### Straight Skeleton
<p float="middle">
  <img src="resources/contour/straightSkeleton.png" alt="" width="49%"/>
  <img src="resources/contour/solubSkeleton.png" alt="" width="49%"/>
</p>

### Uniform straight skeleton
...

### Isolines (topographic contour lines)

<p float="middle">
  <img src="resources/contour/isolines.gif" alt="" width="50%"/>
</p>

### Mitered Offset Curves
Inner and exterior mitered offset curves; based on *miter*, *bevel* or *round* offset styles. 

<p float="middle">
  <img src="resources/contour/miteredInterior.gif" alt="" width="49%"/>
  <img src="resources/contour/miteredExterior.gif" alt="" width="49%"/>
</p>

### Voronoi Diagram
<p float="middle">
  <img src="resources/contour/voronoi1.png" alt="" width="49%"/>
  <img src="resources/contour/voronoi2.png" alt="" width="49%"/>
</p>

### Delaunay Triangulation
Constrained & refined *Delaunay triangulation* of shapes and point sets.

<p float="middle">
  <img src="resources/contour/triangulation1.png" alt="" width="49%"/>
  <img src="resources/contour/triangulation2.png" alt="" width="49%"/>
</p>

### Earcut Triangulation
<p float="middle">
  <img src="resources/contour/earCut.png" alt="" width="49%"/>
  <img src="resources/contour/earCut2.png" alt="" width="49%"/>
</p>

## **Morphology**
*Methods to morph shapes (topology)*
### Buffer
<img src="resources/pts/buffer.gif" alt="" width="50%"/>

### Erosion-Dilation
A negative followed by a positive buffer (in one operation).
<img src="resources/pts/erosionDilation.gif" alt="" width="50%"/>

### Minkowski Addition
Minkowski sum and difference (a.k.a buffer one shape using another shape; pictured: buffering using a rotating & growing triangle).
<p float="middle">
  <img src="resources/morphology/minkSum.gif" alt="" width="49%"/>
  <img src="resources/morphology/minkDiff.gif" alt="" width="49%"/>
</p>

### Simplification
<img src="resources/pts/simplifyVW.gif" alt="" width="50%"/>

### Smoothing
<img src="resources/morphology/smooth.gif" alt="" width="50%"/>

### Concave Hull
<p float="middle">
  <img src="resources/pts/concaveHull.gif" alt="" width="49%"/>
  <img src="resources/pts/concaveHull2.gif" alt="" width="49%"/>
</p>

### Convex Hull
<img src="resources/pts/convexHull.png" alt="" width="50%"/>

### Snap Hull
<img src="resources/pts/snapHull.gif" alt="" width="50%"/>

## **Geometry Processing**

### Point on Perimeter
Find a point some fraction along the perimeter of a shape (with perpendicular offset).

<img src="resources/pts/pointOnPerimeter.gif" alt="" width="50%"/>

### Points on Perimeter
Find *N* points (evenly distributed) along the perimeter of a shape, or points every *D* distance (with optional perpendicular offset).

<p float="middle">
  <img src="resources/pts/pointsOnPerimeter.gif" alt="" width="49%"/>
  <img src="resources/pts/pointsOnPerimeter2.gif" alt="" width="49%"/>
</p>

### Partitioning
Partition a shape into simple (convex) polygons.

<p float="middle">
  <img src="resources/pts/decompose1.png" alt="" width="49%"/>
  <img src="resources/pts/decompose2.png" alt="" width="49%"/>
</p>


## **Geometric Optimization**

### Closest Point
<img src="resources/pts/closestVertex.gif" alt="" width="50%"/>

### Maximum Inscribed Circle
<img src="resources/pts/inscribedCircle.gif" alt="" width="50%"/>

### Minimum Bounding Circle
<img src="resources/pts/minimumBoundingCircle.png" alt="" width="50%"/>

### Minimum Bounding Rectangle
<img src="resources/pts/minimumBoundingRectangle.png" alt="" width="50%"/>


## **Transformation**
PTS provides transformation methods much like Processing's. Notably these methods affect the vertex coordinates of PShapes, unlike Processing's equivalent methods that affect the affine matrix of shapes only (and thereby leave vertex coordinates in-tact).

Methods beyond those offered in Processing are illustrated here:

### Rotate Around
Rotate a shape around its centroid, or some other point.

<p float="middle">
  <img src="resources/transform/rotateCenter.gif" alt="" width="49%"/>
  <img src="resources/transform/rotate.gif" alt="" width="49%"/>
</p>

### Translate To
Translate a shape such that its centroid matches some position.

<img src="resources/transform/translateTo.gif" alt="" width="50%"/>

### Touch Scale
Scale one shape such that it touches another.

<img src="resources/transform/touchScale.gif" alt="" width="50%"/>

### Homothetic Transformation
Projection-transform a shape with respect to a fixed point.

<img src="resources/transform/homothetic.gif" alt="" width="50%"/>

## **Geometric Predicates**

### Intersects
Do shapes intersect with each other?

<img src="resources/predicate/intersect.gif" alt="" width="50%"/>

### Contains Shape
Does one shape fully contain another?

<img src="resources/predicate/contains.gif" alt="" width="50%"/>

### Contains Point
For individual points and point sets.
<p float="middle">
  <img src="resources/predicate/containsPoint.gif" alt="" width="50%"/>
</p>

### Covers
Less strict that contains


### Predicates