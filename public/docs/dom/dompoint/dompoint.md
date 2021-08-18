# DOMPoint.DOMPoint()

The `DOMPoint()` constructor creates and returns a new [`DOMPoint`](../dompoint) object, given the values for some or all of its properties.

You can also create a `DOMPoint` by calling the [`DOMPoint.fromPoint()`](frompoint) static function. That function accepts as input a [`DOMPointInit`](../dompointinit) compatible object, including a `DOMPoint` or [`DOMPointReadOnly`](../dompointreadonly).

## Syntax

    point = new DOMPoint(x, y, z, w);

### Parameters

`x` <span class="badge inline optional">Optional</span>  
The `x` coordinate for the new `DOMPoint`.

`y` <span class="badge inline optional">Optional</span>  
The `y` coordinate for the new `DOMPoint`.

`z` <span class="badge inline optional">Optional</span>  
The `z` coordinate for the new `DOMPoint`.

`w` <span class="badge inline optional">Optional</span>  
The perspective value of the new `DOMPoint`.

## Examples

This example creates a `DOMPoint` representing the top-left corner of the current window, then creates a second point based on the first, which is then offset by 100 pixels both vertically and horizontally.

    var windTopLeft = new DOMPoint(window.screenX, window.screenY);
    var newTopLeft = DOMPoint.fromPoint(windTopLeft);
    newTopLeft.x += 100;
    newTopLeft.y += 100;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompoint-dompoint">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPoint()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DOMPoint`

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

- <span class="page-not-created">`DOMPointReadOnly()`</span>
- [`DOMRect`](../domrect)
- [`DOMMatrix`](../dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/DOMPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/DOMPoint</a>
