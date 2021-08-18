Touch.target
============

Summary
-------

Returns the [`Element`](../element) ([`EventTarget`](../eventtarget)) on which the touch contact started when it was first placed on the surface, even if the touch point has since moved outside the interactive area of that element or even been removed from the document. Note that if the target element is removed from the document, events will still be targeted at it, and hence won't necessarily bubble up to the window or document anymore. If there is any risk of an element being removed while it is being touched, the best practice is to attach the touch listeners directly to the target.

Syntax
------

    var el = touchPoint.target;

### Return value

`el`  
The target element of the [`Touch`](../touch) object.

Example
-------

This example illustrates how to access the [`Touch`](../touch) object's [`Touch.target`](target) property. The [`Touch.target`](target) property is an [`Element`](../element) ([`EventTarget`](../eventtarget)) on which a touch point is started when contact is first placed on the surface.

In following simple code snippet, we assume the user initiates one or more touch contacts on the `source` element. When the `touchstart` event handler for this element is invoked, each touch point's [`Touch.target`](target) property is accessed via the event's [`TouchEvent.targetTouches`](../touchevent/targettouches) list.

    // Register a touchmove listener for the 'source' element
    var src = document.getElementById("source");

    src.addEventListener('touchstart', function(e) {
      // Iterate through the touch points that were activiated
      // for this element.
      for (var i=0; i < e.targetTouches.length; i++) {
        console.log("touchpoint[" + i + "].target = " + e.targetTouches[i].target);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-target">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-target">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`target`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/target</a>
