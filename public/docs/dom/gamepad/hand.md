Gamepad.hand
============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `hand` read-only property of the [`Gamepad`](../gamepad) interface returns an enum defining what hand the controller is being held in, or is most likely to be held in.

Syntax
------

    var myHand = gamepadInstance.hand;

### Value

A `GamepadHand` enum; possible values are:

-   `left` — the left hand.
-   `right` — the right hand.
-   Empty string ("") — this value is returned if the other values are not applicable, e.g. the controller is held in both hands, or would be fine in either.

Examples
--------

TBC

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#dom-gamepad-hand">Gamepad Extensions<br />
<span class="small">The definition of 'hand' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`hand`

No

15-79

55

No

No

No

No

No

55

No

No

No

See also
--------

-   [Gamepad API](../gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/hand" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/hand</a>
