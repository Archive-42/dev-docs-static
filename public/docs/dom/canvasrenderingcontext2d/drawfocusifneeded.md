# CanvasRenderingContext2D.drawFocusIfNeeded()

The ` CanvasRenderingContext2D``.drawFocusIfNeeded() ` method of the Canvas 2D API draws a focus ring around the current or given path, if the specified element is focused.

## Syntax

    void ctx.drawFocusIfNeeded(element);
    void ctx.drawFocusIfNeeded(path, element);

### Parameters

`element`  
The element to check whether it is focused or not.

`path`  
A [`Path2D`](../path2d) path to use.

## Examples

### Managing button focus

This example draws two buttons on a canvas. The `drawFocusIfNeeded()` method is used to draw a focus ring when appropriate.

#### HTML

    <canvas id="canvas">
      <button id="button1">Continue</button>
      <button id="button2">Quit</button>
    </canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const button1 = document.getElementById('button1');
    const button2 = document.getElementById('button2');

    document.addEventListener('focus', redraw, true);
    document.addEventListener('blur', redraw, true);
    canvas.addEventListener('click', handleClick, false);
    redraw();

    function redraw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      drawButton(button1, 20, 20);
      drawButton(button2, 20, 80);
    }

    function handleClick(e) {
      // Calculate click coordinates
      const x = e.clientX - canvas.offsetLeft;
      const y = e.clientY - canvas.offsetTop;

      // Focus button1, if appropriate
      drawButton(button1, 20, 20);
      if (ctx.isPointInPath(x, y)) {
        button1.focus();
      }

      // Focus button2, if appropriate
      drawButton(button2, 20, 80);
      if (ctx.isPointInPath(x, y)) {
        button2.focus();
      }
    }

    function drawButton(el, x, y) {
      const active = document.activeElement === el;
      const width = 150;
      const height = 40;

      // Button background
      ctx.fillStyle = active ? 'pink' : 'lightgray';
      ctx.fillRect(x, y, width, height);

      // Button text
      ctx.font = '15px sans-serif';
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillStyle = active ? 'blue' : 'black';
      ctx.fillText(el.textContent, x + width / 2, y + height / 2);

      // Define clickable area
      ctx.beginPath();
      ctx.rect(x, y, width, height);

      // Draw focus ring, if appropriate
      ctx.drawFocusIfNeeded(el);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-drawfocusifneeded">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.drawFocusIfNeeded' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`drawFocusIfNeeded`

37

14

32

28

No

24

8

37

37

32

28

24

8

3.0

`path_parameter`

37

≤79

No

No

24

9

37

37

No

24

9

3.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawFocusIfNeeded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawFocusIfNeeded</a>
