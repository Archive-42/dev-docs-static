# DOMPointReadOnly.fromPoint()

The static **[`DOMPointReadOnly`](../dompointreadonly)** method `fromPoint()` creates and returns a new `DOMPointReadOnly` object given a source point. The source point is specified as a [`DOMPointInit`](../dompointinit)-compatible object, which includes both [`DOMPoint`](../dompoint) and [`DOMPointReadOnly`](../dompointreadonly).

You can also create a new `DOMPointReadOnly` object using the [`new DOMPointReadOnly()`](dompointreadonly) constructor.

## Syntax

    const point = DOMPointReadOnly.fromPoint(sourcePoint)

### Properties

`sourcePoint`  
A [`DOMPointInit`](../dompointinit)-compliant object, which includes both [`DOMPoint`](../dompoint) and [`DOMPointReadOnly`](../dompointreadonly), from which to take the values of the new point's properties.

### Return value

A new [`DOMPointReadOnly`](../dompointreadonly) object (which is identical to the source point).

## Examples

### Creating a 2D point

This sample creates a 2D point, specifying an inline object that includes the values to use for [`x`](x) and [`y`](y). The `z` and `w` properties are allowed to keep their default values (`0` and `1` respectively).

    const point2D = DOMPointReadOnly.fromPoint({x: 25, y: 25})

### Creating a 3D point using an existing point

This example creates a point, `origPoint`, of type [`DOMPoint`](../dompoint), using [`new DOMPoint()`](../dompoint/dompoint). That point is then used as the input for `fromPoint()` to create a new point, `newPoint`.

    const origPoint = new DOMPoint(25, 25, 100, 0.5)

    const newPoint = DOMPointReadOnly.fromPoint(origPoint)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-frompoint">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'fromPoint()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint</a>
