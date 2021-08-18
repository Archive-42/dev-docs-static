Touch.screenX
=============

Summary
-------

Returns the X coordinate of the touch point relative to the screen, not including any scroll offset.

Syntax
------

    var x = touchItem.screenX;

### Return value

`x`  
The X coordinate of the touch point relative to the screen, not including any scroll offset.

Example
-------

This example illustrates how to access the [`Touch`](../touch) object's [`Touch.screenX`](screenx) and [`Touch.screenY`](screeny) properties. The [`Touch.screenX`](screenx) property is the horizontal (x) coordinate of a touch point relative to the screen in CSS pixels. The [`Touch.screenY`](screeny) property is the vertical coordinate of a touch point relative to the screen in CSS pixels.

In following simple code snippet, we assume the user initiates multiple touch contacts on an element with an id of `source` and then releases contacts with the surface. When the `touchstart` event handler is invoked, each touch point's [`Touch.screenX`](screenx) and [`Touch.screenY`](screeny) coordinates are accessed.

    // Register a touchstart listeners for the 'source' element
    var src = document.getElementById("source");

    src.addEventListener('touchstart', function(e) {
      // Iterate through the touch points and log each screenX/Y coordinate.
      // The unit of each coordinate is CSS pixels.
      var i;
      for (i=0; i < e.touches.length; i++) {
        console.log("touchpoint[" + i + "].screenX = " + e.touches[i].screenX);
        console.log("touchpoint[" + i + "].screenY = " + e.touches[i].screenY);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-screenx">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-screenX">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/screenX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/screenX</a>
