# CanvasRenderingContext2D.font

The ` CanvasRenderingContext2D``.font ` property of the Canvas 2D API specifies the current text style to use when drawing text. This string uses the same syntax as the [CSS font](https://developer.mozilla.org/en-US/docs/Web/CSS/font) specifier.

## Syntax

    ctx.font = value;

### Options

`value`  
A [`DOMString`](../domstring) parsed as CSS [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) value. The default font is 10px sans-serif.

## Examples

### Using a custom font

In this example we use the `font` property to specify a custom font weight, size, and family.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.font = 'bold 48px serif';
    ctx.strokeText('Hello world', 50, 100);

#### Result

### Loading fonts with the CSS Font Loading API

With the help of the [`FontFace`](../fontface) API, you can explicitly load fonts before using them in a canvas.

    let f = new FontFace('test', 'url(x)');

    f.load().then(function() {
      // Ready to use the font in a canvas context
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-font">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.font' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`font`

1

12

3.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

### Gecko-specific notes

- In Gecko-based browsers, such as Firefox, a non-standard and deprecated property `ctx.mozTextStyle` is implemented besides this property. Use `ctx.font` instead.
- In Gecko, when setting a system font as the value of a canvas 2D context's [`font`](font) (e.g., `menu`), getting the font value used to fail to return the expected font (it returns nothing). This is fixed in Firefox's [Quantum/Stylo](https://wiki.mozilla.org/Quantum/Stylo) parallel CSS engine, released in Firefox 57 ([bug 1374885](https://bugzilla.mozilla.org/show_bug.cgi?id=1374885)).

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/font" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/font</a>
