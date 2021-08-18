# CanvasRenderingContext2D.lineWidth

The ` CanvasRenderingContext2D``.lineWidth ` property of the Canvas 2D API sets the thickness of lines.

**Note:** Lines can be drawn with the [`stroke()`](stroke), [`strokeRect()`](strokerect), and [`strokeText()`](stroketext) methods.

## Syntax

    ctx.lineWidth = value;

### Options

`value`  
A number specifying the line width, in coordinate space units. Zero, negative, [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity), and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) values are ignored. This value is `1.0` by default.

## Examples

### Changing line width

This example draws a line and a rectangle, using a line width of 15 units.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.lineWidth = 15;

    ctx.beginPath();
    ctx.moveTo(20, 20);
    ctx.lineTo(130, 130);
    ctx.rect(40, 40, 70, 70);
    ctx.stroke();

#### Result

### More examples

For more examples and explanation about this property, see [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors) in the [Canvas Tutorial](../canvas_api/tutorial).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-linewidth">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.lineWidth' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lineWidth`

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

- In WebKit- and Blink-based Browsers, a non-standard and deprecated method `ctx.setLineWidth()` is implemented in addition to this property.

### Gecko-specific notes

- Starting Gecko 2.0 (Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1), setting `lineWidth` to a negative value no longer throws an exception; instead, it properly ignores non-positive values.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.lineCap`](linecap)
- [`CanvasRenderingContext2D.lineJoin`](linejoin)
- [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineWidth</a>
