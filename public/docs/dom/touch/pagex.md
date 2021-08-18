Touch.pageX
===========

The `Touch.pageX` read-only property returns the X coordinate of the touch point relative to the viewport, including any scroll offset.

Syntax
------

    touchItem.pageX;

### Return value

A `long` representing the X coordinate of the touch point relative to the viewport, including any scroll offset.

Example
-------

This example illustrates how to access the [`Touch`](../touch) object's [`Touch.pageX`](pagex) and [`Touch.pageY`](pagey) properties. The [`Touch.pageX`](pagex) property is the horizontal coordinate of a touch point relative to the viewport (in CSS pixels), including any scroll offset. The [`Touch.pageY`](pagey) property is the vertical coordinate of a touch point relative to the viewport (in CSS pixels), including any scroll offset.

In following simple code snippet, we assume the user initiates one or more touch contacts on the `source` element, moves the touch points and then releases all contacts with the surface. When the `touchmove` event handler is invoked, each touch point's [`Touch.pageX`](pagex) and [`Touch.pageY`](pagey) coordinates are accessed via the event's [`TouchEvent.changedTouches`](../touchevent/changedtouches) list.

    // Register a touchmove listeners for the 'source' element
    var src = document.getElementById("source");

    src.addEventListener('touchmove', function(e) {
      // Iterate through the touch points that have moved and log each
      // of the pageX/Y coordinates. The unit of each coordinate is CSS pixels.
      var i;
      for (i=0; i < e.changedTouches.length; i++) {
        console.log("touchpoint[" + i + "].pageX = " + e.changedTouches[i].pageX);
        console.log("touchpoint[" + i + "].pageY = " + e.changedTouches[i].pageY);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-pagex">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>No change from the previous version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-pageX">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/pageX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/pageX</a>
