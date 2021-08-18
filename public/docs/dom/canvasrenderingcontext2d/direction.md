# CanvasRenderingContext2D.direction

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` CanvasRenderingContext2D``.direction ` property of the Canvas 2D API specifies the current text direction used to draw text.

## Syntax

    ctx.direction = "ltr" || "rtl" || "inherit";

### Options

Possible values:

`"ltr"`  
The text direction is left-to-right.

`"rtl"`  
The text direction is right-to-left.

`"inherit"`  
The text direction is inherited from the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element or the [`Document`](../document) as appropriate. Default value.

The default value is `"inherit"`.

## Examples

### Changing text direction

This example draws two pieces of text. The first one is left-to-right, and the second is right-to-left. Note that "Hi!" in `ltr` becomes "!Hi" in `rtl`.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    ctx.font = '48px serif';
    ctx.fillText('Hi!', 150, 50);
    ctx.direction = 'rtl';
    ctx.fillText('Hi!', 150, 130);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-direction">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.direction' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`direction`

77

39

79

No

No

64

26

9

77

77

No

55

9

12.0

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/direction</a>
