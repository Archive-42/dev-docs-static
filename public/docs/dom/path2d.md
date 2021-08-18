Path2D
======

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Path2D` interface of the Canvas 2D API is used to declare a path that can then be used on a [`CanvasRenderingContext2D`](canvasrenderingcontext2d) object. The [path methods](canvasrenderingcontext2d#paths) of the `CanvasRenderingContext2D` interface are also present on this interface, which gives you the convenience of being able to retain and replay your path whenever desired.

Constructors
------------

[`Path2D()`](path2d/path2d)  
`Path2D` constructor. Creates a new `Path2D` object.

Methods
-------

[`Path2D.addPath()`](path2d/addpath)  
Adds a path to the current path.

[`Path2D.closePath()`](canvasrenderingcontext2d/closepath)  
Causes the point of the pen to move back to the start of the current sub-path. It tries to draw a straight line from the current point to the start. If the shape has already been closed or has only one point, this function does nothing.

[`Path2D.moveTo()`](canvasrenderingcontext2d/moveto)  
Moves the starting point of a new sub-path to the (`x, y`) coordinates.

[`Path2D.lineTo()`](canvasrenderingcontext2d/lineto)  
Connects the last point in the subpath to the (`x, y`) coordinates with a straight line.

[`Path2D.bezierCurveTo()`](canvasrenderingcontext2d/beziercurveto)  
Adds a cubic Bézier curve to the path. It requires three points. The first two points are control points and the third one is the end point. The starting point is the last point in the current path, which can be changed using `moveTo()` before creating the Bézier curve.

[`Path2D.quadraticCurveTo()`](canvasrenderingcontext2d/quadraticcurveto)  
Adds a quadratic Bézier curve to the current path.

[`Path2D.arc()`](canvasrenderingcontext2d/arc)  
Adds an arc to the path which is centered at (`x, y`) position with radius `r` starting at `startAngle` and ending at `endAngle` going in the given direction by `counterclockwise` (defaulting to clockwise).

[`Path2D.arcTo()`](canvasrenderingcontext2d/arcto)  
Adds a circular arc to the path with the given control points and radius, connected to the previous point by a straight line.

[`Path2D.ellipse()`](canvasrenderingcontext2d/ellipse)  
Adds an elliptical arc to the path which is centered at (`x, y`) position with the radii `radiusX` and `radiusY` starting at `startAngle` and ending at `endAngle` going in the given direction by `counterclockwise` (defaulting to clockwise).

[`Path2D.rect()`](canvasrenderingcontext2d/rect)  
Creates a path for a rectangle at position (`x, y`) with a size that is determined by `width` and `height`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#path2d-objects">HTML Living Standard<br />
<span class="small">The definition of 'Path2D' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`Path2D`

36

14

31

No

23

7

37

36

31

24

7

3.0

`Path2D`

36

14

Before Edge 79, the constructor for `Path2D` objects does not support invocation with a string consisting of SVG path data.

31

No

23

7

37

36

31

24

7

3.0

`addPath`

68

79

34

No

55

9

68

68

34

48

9

10.0

See also
--------

-   [`CanvasRenderingContext2D`](canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Path2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Path2D</a>
