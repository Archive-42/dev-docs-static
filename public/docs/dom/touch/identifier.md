Touch.identifier
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Touch.identifier` returns a value uniquely identifying this point of contact with the touch surface. This value remains consistent for every event involving this finger's (or stylus's) movement on the surface until it is lifted off the surface.

Syntax
------

    touchItem.identifier;

### Return value

A `long` that represents the unique ID of the [`Touch`](../touch) object.

Example
-------

    someElement.addEventListener('touchmove', function(e) {
    // Iterate through the list of touch points that changed
    // since the last event and print each touch point's identifier.
      for (var i=0; i < e.changedTouches.length; i++) {
        console.log("changedTouches[" + i + "].identifier = " + e.changedTouches[i].identifier);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-identifier">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-identifier">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`identifier`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/identifier" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/identifier</a>
