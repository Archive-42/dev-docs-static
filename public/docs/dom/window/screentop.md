Window.screenTop
================

The `Window.screenTop` read-only property returns the vertical distance, in CSS pixels, from the top border of the user's browser viewport to the top side of the screen.

**Note**: `screenTop` is an alias of the older [`Window.screenY`](screeny) property. `screenTop` was originally supported only in IE but was introduced everywhere due to popularity.

Syntax
------

    topWindowPos = window.screenTop

### Returns

A number equal to the number of CSS pixels from the top edge of the browser viewport to the top edge of the screen.

Examples
--------

In our [screenleft-screentop](https://mdn.github.io/dom-examples/screenleft-screentop/) example, you'll see a canvas onto which has been drawn a circle. In this example we are using `screenLeft`/`screenTop` plus [`Window.requestAnimationFrame()`](../window/requestanimationframe) to constantly redraw the circle in the same physical position on the screen, even if the window position is moved.

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

Also in the code we include a snippet that detects whether `screenLeft` is supported, and if not, polyfills in `screenLeft`/`screenTop` using [`Window.screenX`](screenx)/[`Window.screenY`](screeny).

    if(!window.screenLeft) {
      window.screenLeft = window.screenX;
      window.screenTop = window.screenY;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-screeny">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Window.screenTop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`screenTop`

1

12

64

5

≤12.1

1

1

18

64

≤12.1

1

1.0

See also
--------

-   [`window.screenLeft`](screenleft)
-   [`Window.screenY`](screeny)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/screenTop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/screenTop</a>
