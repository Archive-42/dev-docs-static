# CanvasRenderingContext2D.textAlign

The ` CanvasRenderingContext2D``.textAlign ` property of the Canvas 2D API specifies the current text alignment used when drawing text.

The alignment is relative to the `x` value of the [`fillText()`](filltext) method. For example, if `textAlign` is `"center"`, then the text's left edge will be at `x - (textWidth / 2)`.

## Syntax

    ctx.textAlign = "left" || "right" || "center" || "start" || "end";

### Options

Possible values:

`"left"`  
The text is left-aligned.

`"right"`  
The text is right-aligned.

`"center"`  
The text is centered.

`"start"`  
The text is aligned at the normal start of the line (left-aligned for left-to-right locales, right-aligned for right-to-left locales).

`"end"`  
The text is aligned at the normal end of the line (right-aligned for left-to-right locales, left-aligned for right-to-left locales).

The default value is `"start"`.

## Examples

### General text alignment

This example demonstrates the three "physical" values of the `textAlign` property: `"left"`, `"center"`, and `"right"`.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    canvas.width = 350;
    const ctx = canvas.getContext('2d');
    const x = canvas.width / 2;

    ctx.beginPath();
    ctx.moveTo(x, 0);
    ctx.lineTo(x, canvas.height);
    ctx.stroke();

    ctx.font = '30px serif';

    ctx.textAlign = 'left';
    ctx.fillText('left-aligned', x, 40);

    ctx.textAlign = 'center';
    ctx.fillText('center-aligned', x, 85);

    ctx.textAlign = 'right';
    ctx.fillText('right-aligned', x, 130);

#### Result

### Direction-dependent text alignment

This example demonstrates the two direction-dependent values of the `textAlign` property: `"start"` and `"end"`. Note that the [`direction`](direction) property is manually specified as `"ltr"`, although this is also the default for English-language text.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.font = '30px serif';
    ctx.direction = 'ltr';

    ctx.textAlign = 'start';
    ctx.fillText('Start-aligned', 0, 50);

    ctx.textAlign = 'end';
    ctx.fillText('End-aligned', canvas.width, 120);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-textalign">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.textAlign' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`textAlign`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/textAlign" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/textAlign</a>
