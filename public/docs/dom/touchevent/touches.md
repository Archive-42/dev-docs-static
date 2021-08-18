TouchEvent.touches
==================

`touches` is a read-only [`TouchList`](../touchlist) listing all the [`Touch`](../touch) objects for touch points that are currently in contact with the touch surface, regardless of whether or not they've changed or what their target element was at `touchstart` time.

You can think of it as how many separate fingers are able to be identified as touching the screen.

Syntax
------

    var touches = touchEvent.touches;

### Return value

`touches`  
A [`TouchList`](../touchlist) listing all the [`Touch`](../touch) objects for touch points that are still in contact with the touch surface, regardless of whether or not they've changed or what their target element was at `touchstart` time.

Example
-------

This example illustrates the [`TouchEvent`](../touchevent) object's [`TouchEvent.touches`](touches) property. The [`TouchEvent.touches`](touches) property is a [`TouchList`](../touchlist) object and containing a list of [`Touch`](../touch) objects for every point of contact currently touching the surface.

In following code snippet, the `touchstart` event handler checks the length of the [`TouchEvent.touches`](touches) list to determine the number of touch points that were activated and then invokes different handlers depending on the number of touch points.

    someElement.addEventListener('touchstart', function(e) {
       // Invoke the appropriate handler depending on the
       // number of touch points.
       switch (e.touches.length) {
         case 1: handle_one_touch(e); break;
         case 2: handle_two_touches(e); break;
         case 3: handle_three_touches(e); break;
         default: console.log("Not supported"); break;
       }
     }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchevent-touches">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchEvent-touches">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`touches`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/touches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/touches</a>
