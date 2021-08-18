TouchEvent.changedTouches
=========================

The `changedTouches` read-only property is a [`TouchList`](../touchlist) whose touch points ([`Touch`](../touch) objects) varies depending on the event type, as follows:

-   For the `touchstart` event, it is a list of the touch points that became active with the current event.
-   For the `touchmove` event, it is a list of the touch points that have changed since the last event.
-   For the `touchend` event, it is a list of the touch points that have been removed from the surface (that is, the set of touch points corresponding to fingers no longer touching the surface).

Syntax
------

    var changes = touchEvent.changedTouches;

### Return value

`changes`  
A [`TouchList`](../touchlist) whose [`Touch`](../touch) objects include all the touch points that contributed to this touch event.

Example
-------

This example illustrates the [`TouchEvent`](../touchevent) object's [`TouchEvent.changedTouches`](changedtouches) property. The [`TouchEvent.changedTouches`](changedtouches) property is a [`TouchList`](../touchlist) object that contains one [`Touch`](../touch) object for each touch point which contributed to the event.

In following code snippet, the `touchmove` event handler iterates through the `changedTouches` list and prints the identifier of each touch point that changed since the last event.

    someElement.addEventListener('touchmove', function(e) {
       // Iterate through the list of touch points that changed
       // since the last event and print each touch point's identifier.
       for (var i=0; i < e.changedTouches.length; i++) {
         console.log("changedTouches[" + i + "].identifier = " + e.changedTouches[i].identifier);
       }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchevent-changedtouches">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchEvent-changedTouches">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`changedTouches`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/changedTouches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/changedTouches</a>
