# Element: mousemove event

The `mousemove` event is fired at an element when a pointing device (usually a mouse) is moved while the cursor's hotspot is inside it.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onmousemove"><code>onmousemove</code></a></td></tr></tbody></table>

## Examples

The following example uses the [`mousedown`](mousedown_event), `mousemove`, and [`mouseup`](mouseup_event) events to allow the user to draw on an HTML5 [canvas](../canvas_api). Its functionality is simple: the thickness of the line is set to 1, and the color is always black.

When the page loads, constants `myPics` and `context` are created to store a reference to the canvas and the 2d context we will use to draw.

Drawing begins when the `mousedown` event fires. First we store the x and y coordinates of the mouse pointer in the variables `x` and `y`, and then set `isDrawing` to true.

As the mouse moves over the page, the `mousemove` event fires. If `isDrawing` is true, the event handler calls the `drawLine` function to draw a line from the stored `x` and `y` values to the current location.

When the `drawLine()` function returns, we adjust the coordinates and then save them in `x` and `y`.

The `mouseup` event draws the final line segment, sets `x` and `y` to `0`, and stops further drawing by setting `isDrawing` to `false`.

### HTML

    <h1>Drawing with mouse events</h1>
    <canvas id="myPics" width="560" height="360"></canvas>

### CSS

    canvas {
      border: 1px solid black;
      width: 560px;
      height: 360px;
    }

### JavaScript

    // When true, moving the mouse draws on the canvas
    let isDrawing = false;
    let x = 0;
    let y = 0;

    const myPics = document.getElementById('myPics');
    const context = myPics.getContext('2d');

    // event.offsetX, event.offsetY gives the (x,y) offset from the edge of the canvas.

    // Add the event listeners for mousedown, mousemove, and mouseup
    myPics.addEventListener('mousedown', e => {
      x = e.offsetX;
      y = e.offsetY;
      isDrawing = true;
    });

    myPics.addEventListener('mousemove', e => {
      if (isDrawing === true) {
        drawLine(context, x, y, e.offsetX, e.offsetY);
        x = e.offsetX;
        y = e.offsetY;
      }
    });

    window.addEventListener('mouseup', e => {
      if (isDrawing === true) {
        drawLine(context, x, y, e.offsetX, e.offsetY);
        x = 0;
        y = 0;
        isDrawing = false;
      }
    });

    function drawLine(context, x1, y1, x2, y2) {
      context.beginPath();
      context.strokeStyle = 'black';
      context.lineWidth = 1;
      context.moveTo(x1, y1);
      context.lineTo(x2, y2);
      context.stroke();
      context.closePath();
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mousemove">UI Events<br />
<span class="small">The definition of 'mousemove' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mousemove">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mousemove' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`mousemove_event`

2

12

6

9

11.6

4

≤37

18

6

12.1

3.2

1.0

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [`mousedown`](mousedown_event)
- [`mouseup`](mouseup_event)
- [`click`](click_event)
- [`dblclick`](dblclick_event)
- [`mouseover`](mouseover_event)
- [`mouseout`](mouseout_event)
- [`mouseenter`](mouseenter_event)
- [`mouseleave`](mouseleave_event)
- [`contextmenu`](contextmenu_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event</a>
