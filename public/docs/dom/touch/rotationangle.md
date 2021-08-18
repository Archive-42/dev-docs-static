Touch.rotationAngle
===================

Summary
-------

Returns the rotation angle, in degrees, of the contact area ellipse defined by [`Touch.radiusX`](radiusx) and [`Touch.radiusY`](radiusy). The value may be between 0 and 90. Together, these three values describe an ellipse that approximates the size and shape of the area of contact between the user and the screen. This may be a relatively large ellipse representing the contact between a fingertip and the screen or a small area representing the tip of a stylus, for example.

**Note:** This attribute has *not* been formally standardized. It is specified in the [Touch Events – Level 2](https://w3c.github.io/touch-events/) <span class="spec-draft">Draft</span> specification and not in [Touch Events](https://www.w3.org/TR/touch-events/) <span class="spec-rec">Recommendation</span>. This attribute is not widely implemented.

Syntax
------

    var angle = touchItem.rotationAngle;

### Return value

`angle`  
The number of degrees of rotation to apply to the described ellipse to align with the contact area between the user and the touch surface.

Example
-------

The [Touch.radiusX example](radiusx#example) includes an example of this property's usage.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-rotationangle">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr></tbody></table>

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

`rotationAngle`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/rotationAngle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/rotationAngle</a>
