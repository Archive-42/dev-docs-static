# DOMPointReadOnly

The `DOMPointReadOnly` interface specifies the coordinate and perspective fields used by [`DOMPoint`](dompoint) to define a 2D or 3D point in a coordinate system.

**Note:** This feature is available in [Web Workers](web_workers_api).

There are two ways to create a new `DOMPointReadOnly` instance. First, you can use its constructor, passing in the values of the parameters for each dimension and, optionally, the perspective:

    /* 2D */
    const point = new DOMPointReadOnly(50, 50);

    /* 3D */
    const point = new DOMPointReadOnly(50, 50, 25);

    /* 3D with perspective */
    const point = new DOMPointReadOnly(100, 100, 100, 1.0);

The other option is to use the static [`DOMPointReadOnly.fromPoint()`](dompointreadonly/frompoint) method:

    const point = DOMPointReadOnly.fromPoint({x: 100, y: 100, z: 50; w: 1.0});

## Constructor

[`DOMPointReadOnly()`](dompointreadonly/dompointreadonly)  
Creates a new `DOMPointReadOnly` object given the values of its coordinates and perspective. To create a point using a`DOMPointInit` object, you can instead use [`DOMPointReadOnly.fromPoint()`](dompointreadonly/frompoint).

## Properties

[`DOMPointReadOnly.x`](dompointreadonly/x) <span class="badge inline readonly">Read only </span>  
The point's horizontal coordinate, `x`.

[`DOMPointReadOnly.y`](dompointreadonly/y) <span class="badge inline readonly">Read only </span>  
The point's vertical coordinate, `y`.

[`DOMPointReadOnly.z`](dompointreadonly/z) <span class="badge inline readonly">Read only </span>  
The point's depth coordinate, `z`.

[`DOMPointReadOnly.w`](dompointreadonly/w) <span class="badge inline readonly">Read only </span>  
The point's perspective value, `w`.

## Static methods

[`DOMPointReadOnly.fromPoint()`](dompointreadonly/frompoint)  
A static method that creates a new `DOMPointReadOnly` object given the coordinates provided in the specified [`DOMPointInit`](dompointinit) object.

## Methods

<span class="page-not-created">`matrixTransform()`</span>  
Applies a matrix transform specified as a <span class="page-not-created">`DOMMatrixInit`</span> object to the `DOMPointReadOnly` object.

[`toJSON()`](dompointreadonly/tojson)  
Returns a JSON representation of the `DOMPointReadOnly` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMPoint">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPoint' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Latest spec version is an ED.</td></tr></tbody></table>

## Browser compatibility

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

`DOMPointReadOnly`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`DOMPointReadOnly`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

`fromPoint`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

`matrixTransform`

61

79

69

No

48

11

61

61

79

45

11

8.0

`toJSON`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

`w`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`worker_support`

61

79

69

No

48

10.1

61

61

79

45

10.3

8.0

`x`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`y`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`z`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

## See also

- [`DOMPoint`](dompoint)
- [`DOMRect`](domrect)
- [`DOMMatrix`](dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly</a>
