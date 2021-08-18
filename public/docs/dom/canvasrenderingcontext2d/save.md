# CanvasRenderingContext2D.save()

The ` CanvasRenderingContext2D``.save() ` method of the Canvas 2D API saves the entire state of the canvas by pushing the current state onto a stack.

### The drawing state

The drawing state that gets saved onto a stack consists of:

- The current transformation matrix.
- The current clipping region.
- The current dash list.
- The current values of the following attributes: [`strokeStyle`](strokestyle), [`fillStyle`](fillstyle), [`globalAlpha`](globalalpha), [`lineWidth`](linewidth), [`lineCap`](linecap), [`lineJoin`](linejoin), [`miterLimit`](miterlimit), [`lineDashOffset`](linedashoffset), [`shadowOffsetX`](shadowoffsetx), [`shadowOffsetY`](shadowoffsety), [`shadowBlur`](shadowblur), [`shadowColor`](shadowcolor), [`globalCompositeOperation`](globalcompositeoperation), [`font`](font), [`textAlign`](textalign), [`textBaseline`](textbaseline), [`direction`](direction), [`imageSmoothingEnabled`](imagesmoothingenabled).

## Syntax

    void ctx.save();

## Examples

### Saving the drawing state

This example uses the `save()` method to save the default state and `restore()` to restore it later, so that you are able to draw a rect with the default state later.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Save the default state
    ctx.save();

    ctx.fillStyle = 'green';
    ctx.fillRect(10, 10, 100, 100);

    // Restore the default state
    ctx.restore();

    ctx.fillRect(150, 40, 100, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-save">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.save' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`save`

1

12

1.5

9

≤12.1

2

1

18

4

≤12.1

1

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.restore()`](restore)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/save" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/save</a>
