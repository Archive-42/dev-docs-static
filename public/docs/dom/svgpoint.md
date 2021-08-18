SVGPoint
========

An `SVGPoint` represents a 2D or 3D point in the SVG coordinate system.

Syntax
------

    retObject = SVGSVGElement.createSVGPoint()

### Value

The returned value is an `SVGPoint` object.

Example
-------

    // Create an SVGPoint in the user coordinate system
    let s = document.getElementById("SVG-ElementID").createSVGPoint();

    // Then, set the x and y values of the returned SVGPoint object
    // (which is the variable `s`)
    s.y = 10;
    s.x = 10;

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

`SVGPoint`

5

12

1.5

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`matrixTransform`

5

12

1.5

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`x`

Yes

12

1.5

9

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`y`

Yes

12

1.5

9

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGPoint</a>
