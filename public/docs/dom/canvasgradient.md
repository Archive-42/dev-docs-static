# CanvasGradient

The `CanvasGradient` interface represents an [opaque object](https://en.wikipedia.org/wiki/Opaque_data_type) describing a gradient. It is returned by the methods [`CanvasRenderingContext2D.createLinearGradient()`](canvasrenderingcontext2d/createlineargradient), [`CanvasRenderingContext2D.createConicGradient()`](canvasrenderingcontext2d/createconicgradient) or [`CanvasRenderingContext2D.createRadialGradient()`](canvasrenderingcontext2d/createradialgradient).

It can be used as a [`fillStyle`](canvasrenderingcontext2d/fillstyle) or [`strokeStyle`](canvasrenderingcontext2d/strokestyle).

## Properties

_As an opaque object, there is no exposed property._

## Methods

[`CanvasGradient.addColorStop()`](canvasgradient/addcolorstop)  
Adds a new stop, defined by an `offset` and a `color`, to the gradient. If the offset is not between `0` and `1`, inclusive, an `INDEX_SIZE_ERR` is raised; if the color can't be parsed as a CSS [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value), a `SYNTAX_ERR` is raised.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/the-canvas-element.html#canvasgradient">HTML Living Standard<br />
<span class="small">The definition of 'CanvasGradient' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`CanvasGradient`

6

12

3.6

Before Firefox 5.0, specifying non-finite values when adding color stops through a call to `addColorStop()` incorrectly throws `SYNTAX_ERR` instead of `INDEX_SIZE_ERR`.

9

9

5.1

≤37

18

4

10.1

6

1.0

`addColorStop`

6

12

3.6

9

9

5.1

≤37

18

4

10.1

6

1.0

## See also

- Creator methods in [`CanvasRenderingContext2D`](canvasrenderingcontext2d).
- The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element and its associated interface, [`HTMLCanvasElement`](htmlcanvaselement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient</a>
