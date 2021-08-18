# CanvasRenderingContext2D.lineDashOffset

The ` CanvasRenderingContext2D``.lineDashOffset ` property of the Canvas 2D API sets the line dash offset, or "phase."

**Note:** Lines are drawn by calling the [`stroke()`](stroke) method.

## Syntax

    ctx.lineDashOffset = value;

`value`  
A float specifying the amount of the line dash offset. The default value is `0.0`.

## Examples

### Offsetting a line dash

This example draws two dashed lines. The first has no dash offset. The second has a dash offset of 4.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.setLineDash([4, 16]);

    // Dashed line with no offset
    ctx.beginPath();
    ctx.moveTo(0, 50);
    ctx.lineTo(300, 50);
    ctx.stroke();

    // Dashed line with offset of 4
    ctx.beginPath();
    ctx.strokeStyle = 'red';
    ctx.lineDashOffset = 4;
    ctx.moveTo(0, 100);
    ctx.lineTo(300, 100);
    ctx.stroke();

#### Result

The line with a dash offset is drawn in red.

### Marching ants

The [marching ants](https://en.wikipedia.org/wiki/Marching_ants) effect is an animation technique often found in selection tools of computer graphics programs. It helps the user to distinguish the selection border from the image background by animating the border.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    let offset = 0;

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.setLineDash([4, 2]);
      ctx.lineDashOffset = -offset;
      ctx.strokeRect(10, 10, 100, 100);
    }

    function march() {
      offset++;
      if (offset > 16) {
        offset = 0;
      }
      draw();
      setTimeout(march, 20);
    }

    march();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-linedashoffset">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.lineDashOffset' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lineDashOffset`

23

12

27

7

11

15

6.1

≤37

25

27

7

14

7

1.5

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.getLineDash()`](getlinedash)
- [`CanvasRenderingContext2D.setLineDash()`](setlinedash)
- [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset</a>
