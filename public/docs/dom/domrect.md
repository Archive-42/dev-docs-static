# DOMRect

**Draft**

This page is not complete.

A `DOMRect` describes the size and position of a rectangle.

The type of box represented by the `DOMRect` is specified by the method or property that returned it. For example, [`VREyeParameters.renderRect`](vreyeparameters/renderrect) from the WebVR API specifies the viewport of a [canvas](htmlcanvaselement) into which visuals for one eye of a head mounted display should be rendered.

It inherits from its parent, [`DOMRectReadOnly`](domrectreadonly).

## Constructor

[`DOMRect()`](domrect/domrect)  
Creates a new `DOMRect` object.

## Properties

_`DOMRect` inherits properties from its parent, [`DOMRectReadOnly`](domrectreadonly). The difference is that they are not read-only anymore._

[`DOMRectReadOnly.x`](domrectreadonly/x)  
The x coordinate of the `DOMRect`'s origin (typically the top-left corner of the rectangle).

[`DOMRectReadOnly.y`](domrectreadonly/y)  
The y coordinate of the `DOMRect`'s origin (typically the top-left corner of the rectangle).

[`DOMRectReadOnly.width`](domrectreadonly/width)  
The width of the `DOMRect`.

[`DOMRectReadOnly.height`](domrectreadonly/height)  
The height of the `DOMRect`.

[`DOMRectReadOnly.top`](domrectreadonly/top)  
Returns the top coordinate value of the `DOMRect` (has the same value as `y`, or `y + height` if `height` is negative.)

[`DOMRectReadOnly.right`](domrectreadonly/right)  
Returns the right coordinate value of the `DOMRect` (has the same value as `x + width`, or `x` if `width` is negative.)

[`DOMRectReadOnly.bottom`](domrectreadonly/bottom)  
Returns the bottom coordinate value of the `DOMRect` (has the same value as `y + height`, or `y` if `height` is negative.)

[`DOMRectReadOnly.left`](domrectreadonly/left)  
Returns the left coordinate value of the `DOMRect` (has the same value as `x`, or `x + width` if `width` is negative.)

## Methods

_`DOMRect` inherits methods from its parent, [`DOMRectReadOnly`](domrectreadonly)._

## Static methods

[`DOMRectReadOnly.fromRect()`](domrectreadonly/fromrect)  
Creates a new `DOMRect` object with a given location and dimensions.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMRect">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMRect' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMRect`

61

2-61

79

12-79

27

3-27

4

48

9.5-48

10.1

4-11

61

2-61

61

18-61

27

4-27

45

10.1-45

10.3

3.2-11

8.0

1.0-8.0

`DOMRect`

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

No

45

10.3

8.0

## See also

- [`DOMPoint`](dompoint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMRect</a>
