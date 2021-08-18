Touch.radiusX
=============

Summary
-------

Returns the X radius of the ellipse that most closely circumscribes the area of contact with the touch surface. The value is in CSS pixels of the same scale as [`Touch.screenX`](screenx).

This value, in combination with [`Touch.radiusY`](radiusy) and [`Touch.rotationAngle`](rotationangle) constructs an ellipse that approximates the size and shape of the area of contact between the user and the screen. This may be a relatively large ellipse representing the contact between a fingertip and the screen or a small area representing the tip of a stylus, for example.

**Note:** This attribute has *not* been formally standardized. It is specified in the [Touch Events – Level 2](https://w3c.github.io/touch-events/) <span class="spec-draft">Draft</span> specification and not in [Touch Events](https://www.w3.org/TR/touch-events/) <span class="spec-rec">Recommendation</span>. This attribute is not widely implemented.

Syntax
------

    var xRadius = touchItem.radiusX;

### Return value

`xRadius`  
The X radius of the ellipse that most closely circumscribes the area of contact with the touch surface.

Example
-------

This example illustrates using the [`Touch`](../touch) interface's [`Touch.radiusX`](radiusx), [`Touch.radiusX`](radiusx) and [`Touch.rotationAngle`](rotationangle) properties. The [`Touch.radiusX`](radiusx) property is the radius of the ellipse which most closely circumscribes the touching area (e.g. finger, stylus) along the axis **indicated** by the touch point's [`Touch.rotationAngle`](rotationangle). Likewise, the [`Touch.radiusY`](radiusy) property is the radius of the ellipse which most closely circumscribes the touching area (e.g. finger, stylus) along the axis **perpendicular** to that indicated by [`Touch.rotationAngle`](rotationangle). The [`Touch.rotationAngle`](rotationangle) is the angle (in degrees) that the ellipse described by `radiusX` and `radiusY` is rotated clockwise about its center.

The following simple code snippet, registers a single handler for the `touchstart`, `touchmove` and `touchend` events. When the `src` element is touched, the element's width and height will be calculate based on the touch point's `radiusX` and `radiusY` values and the element will then be rotated using the touch point's `rotationAngle`.

    <div id="src"> ... </div>

    var src = document.getElementById("src");

    src.addEventListener('touchstart', rotate);
    src.addEventListener('touchmove', rotate);
    src.addEventListener('touchend', rotate);

    function rotate (e) {
      var touch = e.changedTouches.item(0);

      // Turn off default event handling
      e.preventDefault();

      // Rotate element 'src'.
      src.style.width = touch.radiusX * 2 + 'px';
      src.style.height = touch.radiusY * 2 + 'px';
      src.style.transform = "rotate(" + touch.rotationAngle + "deg)";
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-radiusx">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr></tbody></table>

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

`radiusX`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/radiusX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/radiusX</a>
