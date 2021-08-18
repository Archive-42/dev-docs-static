TouchEvent.targetTouches
========================

The `targetTouches` read-only property is a [`TouchList`](../touchlist) listing all the [`Touch`](../touch) objects for touch points that are still in contact with the touch surface **and** whose `touchstart` event occurred inside the same target [`element`](../element) as the current target element.

Syntax
------

    var touches = touchEvent.targetTouches;

### Return value

`touches`  
A [`TouchList`](../touchlist) listing all the [`Touch`](../touch) objects for touch points that are still in contact with the touch surface **and** whose `touchstart` event occurred inside the same target [`element`](../element) as the current target element.

Example
-------

This example illustrates the [`TouchEvent`](../touchevent) object's [`TouchEvent.targetTouches`](targettouches) property. The [`TouchEvent.targetTouches`](targettouches) property is a [`TouchList`](../touchlist) object that includes those TPs that are currently touching the surface *and* started on the element that is the target of the current event. As such, the `targetTouches` list is a strict subset of the `touches` list.

In following code snippet, the function compares the length of the `touches` list to the length of the `targetTouches` list and returns `true` if the lengths are the same and returns `false` otherwise.

    function touches_in_target(ev) {
      // Return true if all of the touches are within the target element;
      // otherwise return false.
      return (ev.touches.length == ev.targetTouches.length ? true : false);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchevent-targettouches">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchEvent-targetTouches">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`targetTouches`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/targetTouches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/targetTouches</a>
