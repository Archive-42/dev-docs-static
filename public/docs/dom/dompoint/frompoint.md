# DOMPoint.fromPoint()

The static **[`DOMPoint`](../dompoint)** method `fromPoint()` creates and returns a new mutable `DOMPoint` object given a source point. The source point is specified as a [`DOMPointInit`](../dompointinit)-compatible object, which includes both [`DOMPoint`](../dompoint) and [`DOMPointReadOnly`](../dompointreadonly).

You can also create a new `DOMPoint` object using the [`new DOMPoint()`](dompoint) constructor.

Although this interface is based on `DOMPointReadOnly`, it is not read-only; the properties within may be changed at will.

## Syntax

    var point = DOMPoint.fromPoint(sourcePoint);

### Properties

`sourcePoint`  
A [`DOMPointInit`](../dompointinit)-compliant object, which includes both [`DOMPoint`](../dompoint) and [`DOMPointReadOnly`](../dompointreadonly), from which to take the values of the new point's properties.

### Return value

A new [`DOMPoint`](../dompoint) object whose coordinate and perspective values are identical to those in the source point. The point's properties are mutable and may be changed at any time.

## Examples

### Creating a mutable point from a read-only point

If you have a [`DOMPointReadOnly`](../dompointreadonly) object, you can easily create a mutable copy of that point:

    var mutablePoint = DOMPoint.fromPoint(readOnlyPoint);

### Creating a 2D point

This sample creates a 2D point, specifying an inline object that includes the values to use for [`x`](../dompointreadonly/x) and [`y`](../dompointreadonly/y). The _z_ and _w_ properties are allowed to keep their default values (0 and 1 respectively).

    var center = DOMPoint.fromPoint({x: 75, y: -50, z: -55, w: 0.25});

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompoint-frompoint">Geometry Interfaces Module Level 1<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/fromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/fromPoint</a>
