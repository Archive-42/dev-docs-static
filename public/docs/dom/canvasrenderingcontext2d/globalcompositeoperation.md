# CanvasRenderingContext2D.globalCompositeOperation

The ` CanvasRenderingContext2D``.globalCompositeOperation ` property of the Canvas 2D API sets the type of compositing operation to apply when drawing new shapes.

See also [Compositing and clipping](../canvas_api/tutorial/compositing) in the [Canvas Tutorial](../canvas_api/tutorial).

## Syntax

    ctx.globalCompositeOperation = type;

`type` is a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) identifying which of the compositing or blending mode operations to use.

### Types

## Examples

### Changing the composite operation

This example uses the `globalCompositeOperation` property to draw two rectangles that exclude themselves where they overlap.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.globalCompositeOperation = 'xor';

    ctx.fillStyle = 'blue';
    ctx.fillRect(10, 10, 100, 100);

    ctx.fillStyle = 'red';
    ctx.fillRect(50, 50, 100, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-globalcompositeoperation">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.globalCompositeOperation' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.fxtf.org/compositing-1/">Compositing and Blending Level 1</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`globalCompositeOperation`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

### WebKit/Blink-specific notes

- In WebKit- and Blink-based Browsers, a non-standard and deprecated method `ctx.setCompositeOperation()` is implemented besides this property.
- Support for `"plus-darker"` and `"darker"` were removed in Chrome 48. Developers looking for a replacement should use `"darken"`.

### Gecko-specific notes

- An early Canvas specification draft specified the value `"darker"`. However, Firefox removed support for `"darker"` in version 4 ([bug 571532](https://bugzilla.mozilla.org/show_bug.cgi?id=571532)). See also [this blog post](https://dropshado.ws/post/77229081704/firefox-doesnt-support-canvas-composite-darker) that suggests using `"difference"` as a way to achieve a similar affect to `"darker"`.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.globalAlpha`](globalalpha)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/globalCompositeOperation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/globalCompositeOperation</a>
