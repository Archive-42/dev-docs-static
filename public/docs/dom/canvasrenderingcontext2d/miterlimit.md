# CanvasRenderingContext2D.miterLimit

The `CanvasRenderingContext2D.miterLimit` property of the Canvas 2D API sets the miter limit ratio.

For more info about miters, see [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors) in the [Canvas tutorial](../canvas_api/tutorial).

## Syntax

    ctx.miterLimit = value;

### Options

`value`  
A number specifying the miter limit ratio, in coordinate space units. Zero, negative, [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity), and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) values are ignored. The default value is `10.0`.

## Examples

### Using the `miterLimit` property

See the chapter [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors#a_demo_of_the_miterlimit_property) in the [Canvas tutorial](../canvas_api/tutorial) for more information.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-miterlimit">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.miterLimit' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`miterLimit`

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

- In WebKit- and Blink-based Browsers, a non-standard and deprecated method `ctx.setMiterLimit()` is implemented in addition to this property.

### Gecko-specific notes

- Starting Gecko 2.0 (Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1), setting `miterLimit` to a negative value no longer throws an exception; instead, it properly ignores non-positive values.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.lineCap`](linecap)
- [`CanvasRenderingContext2D.lineJoin`](linejoin)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/miterLimit</a>
