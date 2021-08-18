# CanvasRenderingContext2D.currentTransform

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The ` CanvasRenderingContext2D``.currentTransform ` property of the Canvas 2D API returns or sets a [`DOMMatrix`](../dommatrix) (current specification) or [`SVGMatrix`](../svgmatrix) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> (old specification) object for the current transformation matrix.

## Syntax

    ctx.currentTransform [= value];

`value`  
A [`DOMMatrix`](../dommatrix) or [`SVGMatrix`](../svgmatrix) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> object to use as the current transformation matrix.

## Examples

### Manually changing the matrix

This example uses the `currentTransform` property to set a transformation matrix. A rectangle is then drawn using that transformation.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let matrix = ctx.currentTransform;
    matrix.a = 1;
    matrix.b = 1;
    matrix.c = 0;
    matrix.d = 1;
    matrix.e = 0;
    matrix.f = 0;
    ctx.currentTransform = matrix;
    ctx.fillRect(0, 0, 100, 100);

#### Result

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

`currentTransform`

32-68

≤18-79

No

See [bug 928150](https://bugzil.la/928150). Firefox also supports the experimental and prefixed properties mozCurrentTransform and mozCurrentTransformInverse which set or get the current (inverse) transformation matrix.

No

19-55

No

See [webkitbug(174278)](https://webkit.org/b/174278).

No

32-68

No

19-48

No

No

`DOMMatrix_return_value`

No

See [bug 637940](https://crbug.com/637940).

No

See [bug 637940](https://crbug.com/637940).

No

No

No

No

See [bug 174278](https://webkit.org/b/174278).

No

See [bug 637940](https://crbug.com/637940).

No

See [bug 637940](https://crbug.com/637940).

No

No

No

No

See [bug 637940](https://crbug.com/637940).

## See also

- The interface defining this property: [`CanvasPattern`](../canvaspattern)
- [`SVGMatrix`](../svgmatrix)
- [`DOMMatrix`](../dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/currentTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/currentTransform</a>
