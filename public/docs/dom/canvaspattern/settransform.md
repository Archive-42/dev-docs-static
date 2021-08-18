# CanvasPattern.setTransform()

The ` CanvasPattern``.setTransform() ` method uses an [`SVGMatrix`](../svgmatrix) or [`DOMMatrix`](../dommatrix) object as the pattern's transformation matrix and invokes it on the pattern.

## Syntax

    void pattern.setTransform(matrix);

### Parameters

`matrix`  
An [`SVGMatrix`](../svgmatrix) or [`DOMMatrix`](../dommatrix) to use as the pattern's transformation matrix.

## Examples

### Using the `setTransform` method

This is just a simple code snippet which uses the `setTransform` method to create a [`CanvasPattern`](../canvaspattern) with the specified pattern transformation from an [`SVGMatrix`](../svgmatrix). The pattern gets applied if you set it as the current [`fillStyle`](../canvasrenderingcontext2d/fillstyle) and gets drawn onto the canvas when using the [`fillRect()`](../canvasrenderingcontext2d/fillrect) method, for example.

#### HTML

    <canvas id="canvas"></canvas>
    <svg id="svg1"></svg>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    var svg1 = document.getElementById('svg1');
    var matrix = svg1.createSVGMatrix();

    var img = new Image();
    img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';

    img.onload = function() {
      var pattern = ctx.createPattern(img, 'repeat');
      pattern.setTransform(matrix.rotate(-45).scale(1.5));
      ctx.fillStyle = pattern;
      ctx.fillRect(0, 0, 400, 400);
    };

Note that newer browser versions started to support [`DOMMatrix`](../dommatrix) as an input to `setTransform()`, so for example you could replace the `SVGMatrix` in the above example with the following:

    const matrix = new DOMMatrix([1, .2, .8, 1, 0, 0]);

Edit the code below and see your changes update live in the canvas:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-canvaspattern-settransform">HTML Living Standard<br />
<span class="small">The definition of 'CanvasPattern.setTransform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setTransform`

68

79

33

No

9

11.1

68

68

33

10.1

11.3

10.0

`dommatrix`

68

79

79

No

55

11.1

68

68

79

48

11.3

10.0

## See also

- The interface defining this method: [`CanvasPattern`](../canvaspattern)
- [`SVGMatrix`](../svgmatrix)
- [`DOMMatrix`](../dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern/setTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern/setTransform</a>
