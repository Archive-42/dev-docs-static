# HTMLCanvasElement.height

The `HTMLCanvasElement.height` property is a positive `integer` reflecting the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-height) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element interpreted in CSS pixels. When the attribute is not specified, or if it is set to an invalid value, like a negative, the default value of `150` is used.

This is one of the two properties, the other being [`HTMLCanvasElement.width`](width), that controls the size of the canvas.

## Syntax

    var pxl = canvas.height;
    canvas.height = pxl;

## Examples

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas" width="300" height="300"></canvas>

You can get the height of the canvas with the following code:

    var canvas = document.getElementById('canvas');
    console.log(canvas.height); // 300

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#attr-canvas-height">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement.height' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/scripting-1.html#attr-canvas-height">HTML 5.1<br />
<span class="small">The definition of 'HTMLCanvasElement.height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/scripting-1.html#attr-canvas-height">HTML5<br />
<span class="small">The definition of 'HTMLCanvasElement.height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a> containing the initial definition.</td></tr></tbody></table>

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

`height`

1

12

1.5

9

9

3

1

18

4

10.1

1

1.0

## See also

- The interface defining it, [`HTMLCanvasElement`](../htmlcanvaselement).
- The other property controlling the size of the canvas, [`HTMLCanvasElement.width`](width).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/height</a>
