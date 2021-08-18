# CanvasRenderingContext2D.shadowColor

The ` CanvasRenderingContext2D``.shadowColor ` property of the Canvas 2D API specifies the color of shadows.

Be aware that the shadow's rendered opacity will be affected by the opacity of the [`fillStyle`](fillstyle) color when filling, and of the [`strokeStyle`](strokestyle) color when stroking.

**Note:** Shadows are only drawn if the `shadowColor` property is set to a non-transparent value. One of the [`shadowBlur`](shadowblur), [`shadowOffsetX`](shadowoffsetx), or [`shadowOffsetY`](shadowoffsety) properties must be non-zero, as well.

## Syntax

    ctx.shadowColor = color;

`color`  
A [`DOMString`](../domstring) parsed as a [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value. The default value is fully-transparent black.

## Examples

### Adding a shadow to shapes

This example adds a shadow to two squares; the first one is filled, and the second one is stroked. The `shadowColor` property sets the shadows' color, while `shadowOffsetX` and `shadowOffsetY` set their position relative to the shapes.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Shadow
    ctx.shadowColor = 'red';
    ctx.shadowOffsetX = 10;
    ctx.shadowOffsetY = 10;

    // Filled rectangle
    ctx.fillRect(20, 20, 100, 100);

    // Stroked rectangle
    ctx.lineWidth = 6;
    ctx.strokeRect(170, 20, 100, 100);

#### Result

### Shadows on translucent shapes

A shadow's opacity is affected by the transparency level of its parent object (even when `shadowColor` specifies a completely opaque value). This example strokes and fills a rectangle with translucent colors.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The resulting alpha value of the fill shadow is `.8 * .2`, or `.16`. The alpha of the stroke shadow is `.8 * .6`, or `.48`.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Shadow
    ctx.shadowColor = 'rgba(255, 0, 0, .8)';
    ctx.shadowBlur = 8;
    ctx.shadowOffsetX = 30;
    ctx.shadowOffsetY = 20;

    // Filled rectangle
    ctx.fillStyle = 'rgba(0, 255, 0, .2)';
    ctx.fillRect(10, 10, 150, 100);

    // Stroked rectangle
    ctx.lineWidth = 10;
    ctx.strokeStyle = 'rgba(0, 0, 255, .6)';
    ctx.strokeRect(10, 10, 150, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-shadowcolor">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.shadowColor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`shadowColor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/shadowColor</a>
