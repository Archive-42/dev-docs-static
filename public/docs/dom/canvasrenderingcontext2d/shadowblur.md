# CanvasRenderingContext2D.shadowBlur

The ` CanvasRenderingContext2D``.shadowBlur ` property of the Canvas 2D API specifies the amount of blur applied to shadows. The default is `0` (no blur).

**Note:** Shadows are only drawn if the [`shadowColor`](shadowcolor) property is set to a non-transparent value. One of the `shadowBlur`, [`shadowOffsetX`](shadowoffsetx), or [`shadowOffsetY`](shadowoffsety) properties must be non-zero, as well.

## Syntax

    ctx.shadowBlur = level;

`level`  
A non-negative float specifying the level of shadow blur, where `0` represents no blur and larger numbers represent increasingly more blur. This value doesn't correspond to a number of pixels, and is not affected by the current transformation matrix. The default value is `0`. Negative, [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity), and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) values are ignored.

## Examples

### Adding a shadow to a shape

This example adds a blurred shadow to a rectangle. The `shadowColor` property sets its color, and `shadowBlur` sets its level of bluriness.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Shadow
    ctx.shadowColor = 'red';
    ctx.shadowBlur = 15;

    // Rectangle
    ctx.fillStyle = 'blue';
    ctx.fillRect(20, 20, 150, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-shadowblur">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.shadowBlur' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`shadowBlur`

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

### WebKit/Blink-specific notes

In WebKit- and Blink-based browsers, the non-standard and deprecated method `ctx.setShadow()` is implemented besides this property.

    setShadow(width, height, blur, color, alpha);
    setShadow(width, height, blur, graylevel, alpha);
    setShadow(width, height, blur, r, g, b, a);
    setShadow(width, height, blur, c, m, y, k, a);

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.shadowColor`](shadowcolor)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowBlur" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowBlur</a>
