# HTMLCanvasElement.mozOpaque

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard `HTMLCanvasElement.mozOpaque` property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`moz-opaque`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-moz-opaque) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. It lets the canvas know whether or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized.

**Note**

This has been standardized as setting the `alpha` option to `false` when creating a drawing context with [`HTMLCanvasElement.getContext()`](getcontext). Use of `mozOpaque` should be avoided. Firefox will stop supporting it in the future.

## Syntax

    var opaque = canvas.mozOpaque;
    canvas.mozOpaque = true;

## Examples

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas" width="300" height="300" moz-opaque></canvas>

You can get or set the `mozOpaque` property. For example, you could conditionally set it to `true` if `mimeType == 'image/jpeg'`, or similar, to gain performance in your application when translucency is not needed.

    var canvas = document.getElementById('canvas');
    console.log(canvas.mozOpaque); // true
    // deactivate it
    canvas.mozOpaque = false;

## Specifications

Not part of any standard.

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

`mozOpaque`

No

No

3.5

No

No

No

No

No

4

No

No

No

## See also

- The interface defining it, [`HTMLCanvasElement`](../htmlcanvaselement).
- The [`moz-opaque`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-moz-opaque) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.
- [Optimizing your JavaScript game for Firefox OS](https://hacks.mozilla.org/2013/05/optimizing-your-javascript-game-for-firefox-os/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozOpaque" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozOpaque</a>
