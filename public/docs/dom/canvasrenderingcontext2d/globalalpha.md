# CanvasRenderingContext2D.globalAlpha

The ` CanvasRenderingContext2D``.globalAlpha ` property of the Canvas 2D API specifies the alpha (transparency) value that is applied to shapes and images before they are drawn onto the canvas.

See also the chapter [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors) in the [Canvas Tutorial](../canvas_api/tutorial).

## Syntax

    ctx.globalAlpha = value;

### Options

`value`  
A number between `0.0` (fully transparent) and `1.0` (fully opaque), inclusive. The default value is `1.0`. Values outside that range, including [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN), will not be set, and `globalAlpha` will retain its previous value.

## Examples

### Drawing translucent shapes

This example uses the `globalAlpha` property to draw two semi-transparent rectangles.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.globalAlpha = 0.5;

    ctx.fillStyle = 'blue';
    ctx.fillRect(10, 10, 100, 100);

    ctx.fillStyle = 'red';
    ctx.fillRect(50, 50, 100, 100);

#### Result

### Overlaying transparent shapes

This example illustrates the effect of overlaying multiple transparent shapes on top of each other. We begin by drawing a solid background composed of four differently colored squares. Next, we set the `globalAlpha` property to `0.2` (20% opaque); this alpha level will apply to all of our transparent shapes. After that, we use a `for` loop to draw a series of circles with increasing radii.

With each new circle, the opacity of the previous circles underneath is effectively increased. If we were to increase the step count (and thus draw more circles), the background would eventually disappear completely from the center of the image.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Draw background
    ctx.fillStyle = '#FD0';
    ctx.fillRect(0, 0, 75, 75);
    ctx.fillStyle = '#6C0';
    ctx.fillRect(75, 0, 75, 75);
    ctx.fillStyle = '#09F';
    ctx.fillRect(0, 75, 75, 75);
    ctx.fillStyle = '#F30';
    ctx.fillRect(75, 75, 75, 75);
    ctx.fillStyle = '#FFF';

    // Set transparency value
    ctx.globalAlpha = 0.2;

    // Draw transparent circles
    for (let i = 0; i < 7; i++) {
      ctx.beginPath();
      ctx.arc(75, 75, 10 + 10 * i, 0, Math.PI * 2, true);
      ctx.fill();
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-globalalpha">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.globalAlpha' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`globalAlpha`

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

### Gecko-specific notes

- Starting with Gecko 5.0, specifying invalid values for `globalAlpha` no longer throws a `SYNTAX_ERR` exception; these are now correctly silently ignored.

### WebKit/Blink-specific notes

- In WebKit- and Blink-based browsers, a non-standard and deprecated method `ctx.setAlpha()` is implemented in addition to this property.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.globalCompositeOperation`](globalcompositeoperation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/globalAlpha" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/globalAlpha</a>
