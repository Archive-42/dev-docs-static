# CanvasRenderingContext2D.canvas

The `CanvasRenderingContext2D.canvas` property, part of the [Canvas API](../canvas_api), is a read-only reference to the [`HTMLCanvasElement`](../htmlcanvaselement) object that is associated with a given context. It might be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if there is no associated [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

## Syntax

    ctx.canvas;

## Examples

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas"></canvas>

... you can get a reference to the canvas element within the `CanvasRenderingContext2D` by using the `canvas` property:

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');
    ctx.canvas // HTMLCanvasElement

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-canvas">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.canvas' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`canvas`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) interface
- [Canvas API](../canvas_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/canvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/canvas</a>
