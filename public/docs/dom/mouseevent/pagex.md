MouseEvent.pageX
================

The `pageX` read-only property of the [`MouseEvent`](../mouseevent) interface returns the X (horizontal) coordinate (in pixels) at which the mouse was clicked, relative to the left edge of the entire document. This includes any portion of the document not currently visible.

Being based on the edge of the document as it is, this property takes into account any horizontal scrolling of the page. For example, if the page is scrolled such that 200 pixels of the left side of the document are scrolled out of view, and the mouse is clicked 100 pixels inward from the left edge of the view, the value returned by `pageX` will be 300.

Originally, this property was defined as a `long` integer. The [CSSOM View Module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_View) redefined it as a `double` float. See the [Browser compatibility](#browser_compatibility) section for details.

See [Page](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_View/Coordinate_systems#page) in [Coordinate systems](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_View/Coordinate_systems) for some additional information about coordinates specified in this fashion.

Syntax
------

    var pageX = MouseEvent.pageX;

### Value

A floating-point number of pixels from the left edge of the *document* at which the mouse was clicked, regardless of any scrolling or viewport positioning that may be in effect.

This property was originally specified in the Touch Events specification as a long integer, but was redefined in the CSSOM View Module to be a double-precision floating-point number to allow for subpixel precision. Even though numeric types both are represented by `Number` in JavaScript, they may be handled differently internally in the browser's code, resulting in potential behavior differences. See [Browser compatibility](#browser_compatibility) to learn which browsers have been updated to use the revised data type.

Example
-------

#### More examples

You can also see an example that demonstrates [how to access the mouse position](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_View/Coordinate_systems#example) information in every available coordinate system.

Let's take a look at a simple example that shows you the mouse's position relative to the page's origin. Since this example is presented in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), that top-left corner is the top-left corner of the frame, not the browser window.

### JavaScript

    var box = document.querySelector(".box");
    var pageX = document.getElementById("x");
    var pageY = document.getElementById("y");

    function updateDisplay(event) {
      pageX.innerText = event.pageX;
      pageY.innerText = event.pageY;
    }

    box.addEventListener("mousemove", updateDisplay, false);
    box.addEventListener("mouseenter", updateDisplay, false);
    box.addEventListener("mouseleave", updateDisplay, false);

The JavaScript code uses [`addEventListener()`](../eventtarget/addeventlistener) to register the function `updateDisplay()` as the event handler for the `mousemove`, `mouseenter`, and `mouseleave` events.

`updateDisplay()` replaces the contents of the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements meant to contain the X and Y coordinates with the values of `pageX` and [`pageY`](pagey).

### HTML

    <div class="box">
      <p>
        Move the mouse around in this box to watch its coordinates change.
      </p>
      <p>
        <code>pageX</code>: <span id="x">n/a</span>
      </p>
      <p>
        <code>pageY</code>: <span id="y">n/a</span>
      </p>
    </div>

The HTML is simple; the box we'll be watching for mouse events on is given the class `"box"`. It has two `<span>` elements, one with the ID `"x"` and one with the ID `"y"`. Those will be updated each time an event occurs to contain the latest mouse coordinates relative to the page.

### CSS

The CSS used for this example is shown below.

    .box {
      width: 400px;
      height: 250px;
      border: 2px solid darkblue;
      background-color: blue;
      color: white;
      font: 16px "Zilla", "Open Sans", "Helvetica", "Arial", sans-serif;
    }

### Result

Try this out here:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mouseevent-pagex">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'pageX' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefined from <code>long</code> to <code>double</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-pageX">Touch Events<br />
<span class="small">The definition of 'pageX' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

Prior to being added to the CSSOM View specification, `pageX` and `pageY` were available on the [`UIEvent`](../uievent) interface in a limited subset of browsers for a short time.

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

`pageX`

45

12

Yes

9

Yes

Yes

45

45

Yes

Yes

Yes

5.0

`long_to_double`

56

≤79

No

?

?

?

56

56

No

?

?

6.0

See also
--------

-   [`MouseEvent.pageY`](pagey)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageX</a>
