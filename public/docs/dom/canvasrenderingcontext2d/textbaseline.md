# CanvasRenderingContext2D.textBaseline

The ` CanvasRenderingContext2D``.textBaseline ` property of the Canvas 2D API specifies the current text baseline used when drawing text.

## Syntax

    ctx.textBaseline = "top" || "hanging" || "middle" || "alphabetic" || "ideographic" || "bottom";

### Options

Possible values:

`"top"`  
The text baseline is the top of the em square.

`"hanging"`  
The text baseline is the hanging baseline. (Used by Tibetan and other Indic scripts.)

`"middle"`  
The text baseline is the middle of the em square.

`"alphabetic"`  
The text baseline is the normal alphabetic baseline. Default value.

`"ideographic"`  
The text baseline is the ideographic baseline; this is the bottom of the body of the characters, if the main body of characters protrudes beneath the alphabetic baseline. (Used by Chinese, Japanese, and Korean scripts.)

`"bottom"`  
The text baseline is the bottom of the bounding box. This differs from the ideographic baseline in that the ideographic baseline doesn't consider descenders.

The default value is `"alphabetic"`.

## Examples

### Comparison of property values

This example demonstrates the various `textBaseline` property values.

#### HTML

    <canvas id="canvas" width="550" height="500"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    const baselines = ['top', 'hanging', 'middle', 'alphabetic', 'ideographic', 'bottom'];
    ctx.font = '36px serif';
    ctx.strokeStyle = 'red';

    baselines.forEach(function (baseline, index) {
      ctx.textBaseline = baseline;
      const y = 75 + index * 75;
      ctx.beginPath();
      ctx.moveTo(0, y + 0.5);
      ctx.lineTo(550, y + 0.5);
      ctx.stroke();
      ctx.fillText('Abcdefghijklmnop (' + baseline + ')', 0, y);
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-textbaseline">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.textBaseline' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`textBaseline`

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

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/textBaseline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/textBaseline</a>
