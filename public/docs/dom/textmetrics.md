TextMetrics
===========

The `TextMetrics` interface represents the dimensions of a piece of text in the canvas; a `TextMetrics` instance can be retrieved using the [`CanvasRenderingContext2D.measureText()`](canvasrenderingcontext2d/measuretext) method.

Properties
----------

 [`TextMetrics.width`](textmetrics/width) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the calculated width of a segment of inline text in CSS pixels. It takes into account the current font of the context.

 [`TextMetrics.actualBoundingBoxLeft`](textmetrics/actualboundingboxleft) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the alignment point given by the [`CanvasRenderingContext2D.textAlign`](canvasrenderingcontext2d/textalign) property to the left side of the bounding rectangle of the given text, in CSS pixels. The distance is measured parallel to the baseline.

 [`TextMetrics.actualBoundingBoxRight`](textmetrics/actualboundingboxright) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the alignment point given by the [`CanvasRenderingContext2D.textAlign`](canvasrenderingcontext2d/textalign) property to the right side of the bounding rectangle of the given text, in CSS pixels. The distance is measured parallel to the baseline.

 [`TextMetrics.fontBoundingBoxAscent`](textmetrics/fontboundingboxascent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) attribute to the top of the highest bounding rectangle of all the fonts used to render the text, in CSS pixels.

 [`TextMetrics.fontBoundingBoxDescent`](textmetrics/fontboundingboxdescent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) attribute to the bottom of the bounding rectangle of all the fonts used to render the text, in CSS pixels.

 [`TextMetrics.actualBoundingBoxAscent`](textmetrics/actualboundingboxascent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) attribute to the top of the bounding rectangle used to render the text, in CSS pixels.

 [`TextMetrics.actualBoundingBoxDescent`](textmetrics/actualboundingboxdescent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) attribute to the bottom of the bounding rectangle used to render the text, in CSS pixels.

 [`TextMetrics.emHeightAscent`](textmetrics/emheightascent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property to the top of the *em* square in the line box, in CSS pixels.

 [`TextMetrics.emHeightDescent`](textmetrics/emheightdescent) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property to the bottom of the *em* square in the line box, in CSS pixels.

 [`TextMetrics.hangingBaseline`](textmetrics/hangingbaseline) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property to the hanging baseline of the line box, in CSS pixels.

 [`TextMetrics.alphabeticBaseline`](textmetrics/alphabeticbaseline) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property to the alphabetic baseline of the line box, in CSS pixels.

 [`TextMetrics.ideographicBaseline`](textmetrics/ideographicbaseline) <span class="badge inline readonly">Read only </span>   
Is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property to the ideographic baseline of the line box, in CSS pixels.

Examples
--------

### Baselines illustrated

This example demonstrates the baselines the `TextMetrics` object holds. The default baseline is the `alphabeticBaseline`. See also the [`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline) property.

#### HTML

    <canvas id="canvas" width="550" height="500"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    const baselinesAboveAlphabetic = ['fontBoundingBoxAscent', 'actualBoundingBoxAscent',
                       'emHeightAscent', 'hangingBaseline'];
    const baselinesBelowAlphabetic = ['ideographicBaseline', 'emHeightDescent',
                       'actualBoundingBoxDescent', 'fontBoundingBoxDescent'];
    const baselines = [...baselinesAboveAlphabetic, ...baselinesBelowAlphabetic];
    ctx.font = '25px serif';
    ctx.strokeStyle = 'red';

    baselines.forEach(function (baseline, index) {
      let text = 'Abcdefghijklmnop (' + baseline + ')';
      let textMetrics = ctx.measureText(text);
      let y = 50 + index * 50;
      ctx.beginPath();
      ctx.fillText(text, 0, y);
      let lineY = y - Math.abs(textMetrics[baseline]);
      if (baselinesBelowAlphabetic.includes(baseline)) {
        lineY = y + Math.abs(textMetrics[baseline]);
      }
      ctx.moveTo(0, lineY);
      ctx.lineTo(550, lineY);
      ctx.stroke();

    });

#### Result

### Measuring text width

When measuring the x-direction of a piece of text, the sum of `actualBoundingBoxLeft` and `actualBoundingBoxRight` can be wider than the width of the inline box (`width`), due to slanted/italic fonts where characters overhang their advance width.

It can therefore be useful to use the sum of `actualBoundingBoxLeft` and `actualBoundingBoxRight` as a more accurate way to get the absolute text width:

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const text = 'Abcdefghijklmnop';
    ctx.font = 'italic 50px serif';
    const textMetrics = ctx.measureText(text);

    console.log(textMetrics.width);
    // 459.8833312988281

    console.log(Math.abs(textMetrics.actualBoundingBoxLeft) +
                Math.abs(textMetrics.actualBoundingBoxRight));
    // 462.8833333333333

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/the-canvas-element.html#textmetrics">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

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

`TextMetrics`

1

12

1.5

9

9

3.1

1

18

31

10.1

Yes

1.0

`actualBoundingBoxAscent`

77

Yes-77

79

74

No

64

Yes

77

77

Yes-77

No

55

Yes

12.0

`actualBoundingBoxDescent`

77

Yes-77

79

74

No

64

Yes

77

77

Yes-77

No

55

Yes

12.0

`actualBoundingBoxLeft`

77

Yes-77

79

74

No

64

Yes

77

77

Yes-77

No

55

Yes

12.0

`actualBoundingBoxRight`

77

Yes-77

79

74

No

64

Yes

77

77

Yes-77

No

55

Yes

12.0

`alphabeticBaseline`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

`emHeightAscent`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

`emHeightDescent`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

`fontBoundingBoxAscent`

87

Yes

79

74

No

73

Yes

87

87

Yes

No

No

Yes

14.0

`fontBoundingBoxDescent`

87

Yes

79

74

No

73

Yes

87

87

Yes

No

No

No

14.0

`hangingBaseline`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

`ideographicBaseline`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

`width`

4

12

1.5

9

9

3.1

Yes

Yes

31

Yes

3.2

Yes

See also
--------

-   Creator method in [`CanvasRenderingContext2D`](canvasrenderingcontext2d)
-   The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element and its associated interface, [`HTMLCanvasElement`](htmlcanvaselement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics</a>
