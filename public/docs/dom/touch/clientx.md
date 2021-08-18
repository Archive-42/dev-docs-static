Touch.clientX
=============

The `Touch.clientX` read-only property returns the X coordinate of the touch point relative to the viewport, not including any scroll offset.

Syntax
------

    touchItem.clientX;

### Return value

A `long` representing the X coordinate of the touch point relative to the viewport, not including any scroll offset.

Example
-------

This example illustrates using the [`Touch`](../touch) object's [`Touch.clientX`](clientx) and [`Touch.clientY`](clienty) properties. The [`Touch.clientX`](clientx) property is the horizontal coordinate of a touch point relative to the browser's viewport excluding any scroll offset. The [`Touch.clientY`](clienty) property is the vertical coordinate of the touch point relative to the browser's viewport excluding any scroll offset .

In this example, we assume the user initiates a touch on an element with an id of `source`, moves within the element or out of the element and then releases contact with the surface. When the [`touchend`](../element/touchend_event) event handler is invoked, the changes in the [`Touch.clientX`](clientx) and [`Touch.clientY`](clienty) coordinates, from the starting touch point to the ending touch point, are calculated.

    // Register touchstart and touchend listeners for element 'source'
    var src = document.getElementById("source");
    var clientX, clientY;

    src.addEventListener('touchstart', function(e) {
      // Cache the client X/Y coordinates
      clientX = e.touches[0].clientX;
      clientY = e.touches[0].clientY;
    }, false);

    src.addEventListener('touchend', function(e) {
      var deltaX, deltaY;

      // Compute the change in X and Y coordinates.
      // The first touch point in the changedTouches
      // list is the touch point that was just removed from the surface.
      deltaX = e.changedTouches[0].clientX - clientX;
      deltaY = e.changedTouches[0].clientY - clientY;

      // Process the data ...
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-clientx">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-clientX">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clientX`

22

≤18

52

Touch events support has been fixed and reenabled in Windows desktop platforms.

18-24

Web compatibility issues seen in [bug 888304](https://bugzil.la/888304).

No

Yes

No

Yes

Yes

6

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/clientX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/clientX</a>
