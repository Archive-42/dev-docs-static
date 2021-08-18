Touch()
=======

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Touch()` constructor creates a new [`Touch`](../touch) object.

Syntax
------

     touch = new Touch(touchInit);

### Arguments

*touchInit*  
Is a `TouchInit` dictionary, having the following fields:

-   `"identifier"`, required, of type `long`, that is the identification number for the touch point.
-   `"target"`, required, of type [`EventTarget`](../eventtarget), the item at which the touch point started when it was first placed on the surface.
-   `"clientX"`, optional and defaulting to `0`, of type `double`, that is the horizontal position of the touch on the client window of user's screen, excluding any scroll offset.
-   `"clientY"`, optional and defaulting to `0`, of type `double`, that is the vertical position of the touch on the client window of the user's screen, excluding any scroll offset.
-   `"screenX"`, optional and defaulting to `0`, of type `double`, that is the horizontal position of the touch on the user's screen.
-   `"screenY"`, optional and defaulting to `0`, of type `double`, that is the vertical position of the touch on the user's screen.
-   `"pageX"`, optional and defaulting to `0`, of type `double`, that is the horizontal position of the touch on the client window of user's screen, including any scroll offset.
-   `"pageY"`, optional and defaulting to `0`, of type `double`, that is the vertical position of the touch on the client window of the user's screen, including any scroll offset.
-   `"radiusX"`, optional and defaulting to `0`, of type `float`, that is the radius of the ellipse which most closely circumscribes the touching area (e.g. finger, stylus) along the axis indicated by rotationAngle, in CSS pixels of the same scale as screenX; `0` if no value is known. The value must not be negative.
-   `"radiusY"`, optional and defaulting to `0`, of type `float`, that is the radius of the ellipse which most closely circumscribes the touching area (e.g. finger, stylus) along the axis perpendicular to that indicated by rotationAngle, in CSS pixels of the same scale as screenY; `0` if no value is known. The value must not be negative.
-   `"rotationAngle"`, optional and defaulting to `0`, of type `float`, that is the angle (in degrees) that the ellipse described by radiusX and radiusY is rotated clockwise about its center; `0` if no value is known. The value must be greater than or equal to `0` and less than `90`. If the ellipse described by radiusX and radiusY is circular, then rotationAngle has no effect. The user agent may use `0` as the value in this case, or it may use any other value in the allowed range. (For example, the user agent may use the rotationAngle value from the previous touch event, to avoid sudden changes.).
-   `"force"`, optional and defaulting to `0`, of type `float`, that is the relative value of pressure applied, in the range `0` to `1`, where `0` is no pressure, and `1` is the highest level of pressure the touch device is capable of sensing; `0` if no value is known. In environments where force is known, the absolute pressure represented by the force attribute, and the sensitivity in levels of pressure, may vary.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#touchevent-interface">Touch Events – Level 2<br />
<span class="small">The definition of 'TouchEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Touch`

48

79

46

No

35

No

48

48

6

Yes

Yes

5.0

See also
--------

-   [`TouchEvent`](../touchevent), the interface of the objects it constructs  
    .

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/Touch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/Touch</a>
