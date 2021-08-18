Window.screenX
==============

The `Window.screenX` read-only property returns the horizontal distance, in CSS pixels, of the left border of the user's browser viewport to the left side of the screen.

**Note**: An alias of `screenX` was implemented across modern browsers in more recent times — [`Window.screenLeft`](screenleft). This was originally supported only in IE but was introduced everywhere due to popularity.

Syntax
------

    leftWindowPos = window.screenX

### Returns

A number equal to the number of CSS pixels from the left edge of the browser viewport to the left edge of the screen.

Examples
--------

In our [screenleft-screentop](https://mdn.github.io/dom-examples/screenleft-screentop/) ([source code](https://github.com/mdn/dom-examples/blob/master/screenleft-screentop/index.html)) example, you'll see a canvas onto which has been drawn a circle. In this example we are using [`Window.screenLeft`](screenleft)/[`Window.screenTop`](screentop) plus [`Window.requestAnimationFrame()`](../window/requestanimationframe) to constantly redraw the circle in the same physical position on the screen, even if the window position is moved.

    initialLeft = window.screenLeft + canvasElem.offsetLeft;
    initialTop = window.screenTop + canvasElem.offsetTop;

    function positionElem() {
      let newLeft = window.screenLeft + canvasElem.offsetLeft;
      let newTop = window.screenTop + canvasElem.offsetTop;

      let leftUpdate = initialLeft - newLeft;
      let topUpdate = initialTop - newTop;

      ctx.fillStyle = 'rgb(0, 0, 0)';
      ctx.fillRect(0, 0, width, height);
      ctx.fillStyle = 'rgb(0, 0, 255)';
      ctx.beginPath();
      ctx.arc(leftUpdate + (width/2), topUpdate + (height/2) + 35, 50, degToRad(0), degToRad(360), false);
      ctx.fill();

      pElem.textContent = 'Window.screenLeft: ' + window.screenLeft + ', Window.screenTop: ' + window.screenTop;

      window.requestAnimationFrame(positionElem);
    }

    window.requestAnimationFrame(positionElem);

These work in exactly the same way as `screenX`/`screenY`.

Also in the code we include a snippet that detects whether `screenLeft` is supported, and if not, polyfills in `screenLeft`/`screenTop` using `screenX`/`screenY`.

    if(!window.screenLeft) {
      window.screenLeft = window.screenX;
      window.screenTop = window.screenY;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-screenx">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Window.screenX' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`screenX`

1

12

1

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

9

≤12.1

1

1

18

4

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

≤12.1

1

1.0

See also
--------

-   [`window.screenLeft`](screenleft)
-   [`Window.screenY`](screeny)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/screenX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/screenX</a>
