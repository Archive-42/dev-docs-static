# CanvasPattern

The `CanvasPattern` interface represents an [opaque object](https://en.wikipedia.org/wiki/Opaque_data_type) describing a pattern, based on an image, a canvas, or a video, created by the [`CanvasRenderingContext2D.createPattern()`](canvasrenderingcontext2d/createpattern) method.

It can be used as a [`fillStyle`](canvasrenderingcontext2d/fillstyle) or [`strokeStyle`](canvasrenderingcontext2d/strokestyle).

## Properties

_As an opaque object, this has no exposed property._

## Methods

_There are no inherited method._

[`CanvasPattern.setTransform()`](canvaspattern/settransform)  
Applies an [`SVGMatrix`](svgmatrix) or [`DOMMatrix`](dommatrix) representing a linear transform to the pattern.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/the-canvas-element.html#canvaspattern">HTML Living Standard<br />
<span class="small">The definition of 'CanvasPattern' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>setTransform()</code> method in v5.</td></tr></tbody></table>

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

`CanvasPattern`

4

12

3.6

9

9

3.1

≤37

18

4

10.1

3.2

1.0

`setTransform`

68

79

33

No

9

11.1

68

68

33

10.1

11.3

10.0

## See also

- [`CanvasRenderingContext2D.createPattern()`](canvasrenderingcontext2d/createpattern)
- The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element and its associated interface, [`HTMLCanvasElement`](htmlcanvaselement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern</a>
