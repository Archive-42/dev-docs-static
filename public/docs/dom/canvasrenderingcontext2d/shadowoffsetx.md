# CanvasRenderingContext2D.shadowOffsetX

The ` CanvasRenderingContext2D``.shadowOffsetX ` property of the Canvas 2D API specifies the distance that shadows will be offset horizontally.

**Note:** Shadows are only drawn if the [`shadowColor`](shadowcolor) property is set to a non-transparent value. One of the [`shadowBlur`](shadowblur), `shadowOffsetX`, or [`shadowOffsetY`](shadowoffsety) properties must be non-zero, as well.

## Syntax

    ctx.shadowOffsetX = offset;

`offset`  
A float specifying the distance that shadows will be offset horizontally. Positive values are to the right, and negative to the left. The default value is `0` (no horizontal offset). [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) values are ignored.

## Examples

### Moving a shadow horizontally

This example adds a blurred shadow to a rectangle. The [`shadowColor`](shadowcolor) property sets its color, `shadowOffsetX` sets its offset 25 units to the right, and [`shadowBlur`](shadowblur) gives it a blur level of 10.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Shadow
    ctx.shadowColor = 'red';
    ctx.shadowOffsetX = 25;
    ctx.shadowBlur = 10;

    // Rectangle
    ctx.fillStyle = 'blue';
    ctx.fillRect(20, 20, 150, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-shadowoffsetx">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.shadowOffsetX' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`shadowOffsetX`

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

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.shadowOffsetY`](shadowoffsety)
- [`CanvasRenderingContext2D.shadowColor`](shadowcolor)
- [`CanvasRenderingContext2D.shadowBlur`](shadowblur)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowOffsetX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowOffsetX</a>
