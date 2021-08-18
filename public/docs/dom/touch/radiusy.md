Touch.radiusY
=============

Summary
-------

Returns the Y radius of the ellipse that most closely circumscribes the area of contact with the touch surface. The value is in CSS pixels of the same scale as [`Touch.screenX`](screenx).

This value, in combination with [`Touch.radiusX`](radiusx) and [`Touch.rotationAngle`](rotationangle) constructs an ellipse that approximates the size and shape of the area of contact between the user and the screen. This may be a large ellipse representing the contact between a fingertip and the screen or a small one representing the tip of a stylus, for example.

**Note:** This attribute has *not* been formally standardized. It is specified in the [Touch Events – Level 2](https://w3c.github.io/touch-events/) <span class="spec-draft">Draft</span> specification and not in [Touch Events](https://www.w3.org/TR/touch-events/) <span class="spec-rec">Recommendation</span>. This attribute is not widely implemented.

Syntax
------

    var yRadius = touchItem.radiusY;

### Return value

`yRadius`  
The Y radius of the ellipse that most closely circumscribes the area of contact with the screen.

Example
-------

The [Touch.radiusX example](radiusx#example) includes an example of this property's usage.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-radiusy">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr></tbody></table>

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

`radiusY`

43

≤79

?

No

Yes

No

43

43

Yes

Yes

Yes

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/radiusY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/radiusY</a>
