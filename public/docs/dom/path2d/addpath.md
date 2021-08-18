Path2D.addPath()
================

The `Path2D``.addPath()` method of the Canvas 2D API adds one [`Path2D`](../path2d) object to another `Path2D` object.

Syntax
------

    void path.addPath(path [, transform]);

### Parameters

`path`  
A [`Path2D`](../path2d) path to add.

 `transform` <span class="badge inline optional">Optional</span>   
A [`DOMMatrix`](../dommatrix) to be used as the transformation matrix for the path that is added. (Technically a `DOMMatrixInit` object).

Examples
--------

### Adding a path to an existing path

This example adds one path to another.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

First, we create two separate [`Path2D`](../path2d) objects, each of which contains a rectangle made using the [`rect()`](../canvasrenderingcontext2d/rect) method. We then create a matrix using [`document.createElementNS()`](../document/createelementns) and `createSVGMatrix()`. We then add the second path to the first using `addPath()`, also applying the matrix to move the second path to the right. Finally, we draw the first path (which now contains both rectangles) using [`fill()`](../canvasrenderingcontext2d/fill).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create first path and add a rectangle
    let p1 = new Path2D();
    p1.rect(0, 0, 100, 150);

    // Create second path and add a rectangle
    let p2 = new Path2D();
    p2.rect(0, 0, 100, 75);

    // Create transformation matrix that moves 200 points to the right
    let m = document.createElementNS('http://www.w3.org/2000/svg', 'svg').createSVGMatrix();
    m.a = 1; m.b = 0;
    m.c = 0; m.d = 1;
    m.e = 200; m.f = 0;

    // Add second path to the first path
    p1.addPath(p2, m);

    // Draw the first path
    ctx.fill(p1);

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-path2d-addpath">HTML Living Standard<br />
<span class="small">The definition of 'Path2D.addPath()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   The interface defining this method: [`Path2D`](../path2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Path2D/addPath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Path2D/addPath</a>
