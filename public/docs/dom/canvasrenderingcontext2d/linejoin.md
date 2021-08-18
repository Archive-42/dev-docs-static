# CanvasRenderingContext2D.lineJoin

The ` CanvasRenderingContext2D``.lineJoin ` property of the Canvas 2D API determines the shape used to join two line segments where they meet.

This property has no effect wherever two connected segments have the same direction, because no joining area will be added in this case. Degenerate segments with a length of zero (i.e., with all endpoints and control points at the exact same position) are also ignored.

**Note:** Lines can be drawn with the [`stroke()`](stroke), [`strokeRect()`](strokerect), and [`strokeText()`](stroketext) methods.

## Syntax

    ctx.lineJoin = "bevel" || "round" || "miter";

### Options

There are three possible values for this property: `"round"`, `"bevel"`, and `"miter"`. The default is `"miter"`.

<img src="data:image/png;base64,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" width="190" height="190" />

`"round"`  
Rounds off the corners of a shape by filling an additional sector of disc centered at the common endpoint of connected segments. The radius for these rounded corners is equal to the line width.

`"bevel"`  
Fills an additional triangular area between the common endpoint of connected segments, and the separate outside rectangular corners of each segment.

`"miter"`  
Connected segments are joined by extending their outside edges to connect at a single point, with the effect of filling an additional lozenge-shaped area. This setting is affected by the [`miterLimit`](miterlimit) property. Default value.

## Examples

### Changing the joins in a path

This example applies rounded line joins to a path.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.lineWidth = 20;
    ctx.lineJoin = 'round';
    ctx.beginPath();
    ctx.moveTo(20, 20);
    ctx.lineTo(190, 100);
    ctx.lineTo(280, 20);
    ctx.lineTo(280, 150);
    ctx.stroke();

#### Result

### Comparison of line joins

The example below draws three different paths, demonstrating each of the three `lineJoin` options.

    var ctx = document.getElementById('canvas').getContext('2d');
    var lineJoin = ['round', 'bevel', 'miter'];
    ctx.lineWidth = 10;

    for (let i = 0; i < lineJoin.length; i++) {
      ctx.lineJoin = lineJoin[i];
      ctx.beginPath();
      ctx.moveTo(-5, 5 + i * 40);
      ctx.lineTo(35, 45 + i * 40);
      ctx.lineTo(75, 5 + i * 40);
      ctx.lineTo(115, 45 + i * 40);
      ctx.lineTo(155, 5 + i * 40);
      ctx.stroke();
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-linejoin">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.lineJoin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lineJoin`

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

- In WebKit- and Blink-based Browsers, a non-standard and deprecated method `ctx.setLineJoin()` is implemented in addition to this property.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.lineCap`](linecap)
- [`CanvasRenderingContext2D.lineWidth`](linewidth)
- [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin</a>
