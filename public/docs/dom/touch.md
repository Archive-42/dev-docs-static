Touch
=====

The `Touch` interface represents a single contact point on a touch-sensitive device. The contact point is commonly a finger or stylus and the device may be a touchscreen or trackpad.

The [`Touch.radiusX`](touch/radiusx), [`Touch.radiusY`](touch/radiusy), and [`Touch.rotationAngle`](touch/rotationangle) describe the area of contact between the user and the screen, the *touch area*. This can be helpful when dealing with imprecise pointing devices such as fingers. These values are set to describe an ellipse that as closely as possible matches the entire area of contact (such as the user's fingertip). <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

**Note:** Many of the properties' values are hardware-dependent; for example, if the device doesn't have a way to detect the amount of pressure placed on the surface, the `force` value will always be 0. This may also be the case for `radiusX` and `radiusY`; if the hardware reports only a single point, these values will be 1.

Constructor
-----------

 [`Touch()`](touch/touch) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates a Touch object.

Properties
----------

*This interface has no parent, and doesn't inherits or implements any other property.*

### Basic properties

 [`Touch.identifier`](touch/identifier) <span class="badge inline readonly">Read only </span>   
Returns a unique identifier for this `Touch` object. A given touch point (say, by a finger) will have the same identifier for the duration of its movement around the surface. This lets you ensure that you're tracking the same touch all the time.

 [`Touch.screenX`](touch/screenx) <span class="badge inline readonly">Read only </span>   
Returns the X coordinate of the touch point relative to the left edge of the screen.

 [`Touch.screenY`](touch/screeny) <span class="badge inline readonly">Read only </span>   
Returns the Y coordinate of the touch point relative to the top edge of the screen.

 [`Touch.clientX`](touch/clientx) <span class="badge inline readonly">Read only </span>   
Returns the X coordinate of the touch point relative to the left edge of the browser viewport, not including any scroll offset.

 [`Touch.clientY`](touch/clienty) <span class="badge inline readonly">Read only </span>   
Returns the Y coordinate of the touch point relative to the top edge of the browser viewport, not including any scroll offset.

 [`Touch.pageX`](touch/pagex) <span class="badge inline readonly">Read only </span>   
Returns the X coordinate of the touch point relative to the left edge of the document. Unlike `clientX`, this value includes the horizontal scroll offset, if any.

 [`Touch.pageY`](touch/pagey) <span class="badge inline readonly">Read only </span>   
Returns the Y coordinate of the touch point relative to the top of the document. Unlike `clientY,` this value includes the vertical scroll offset, if any.

 [`Touch.target`](touch/target) <span class="badge inline readonly">Read only </span>   
Returns the [`Element`](element) on which the touch point started when it was first placed on the surface, even if the touch point has since moved outside the interactive area of that element or even been removed from the document.

### Touch area

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

 [`Touch.radiusX`](touch/radiusx) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the X radius of the ellipse that most closely circumscribes the area of contact with the screen. The value is in pixels of the same scale as `screenX`.

 [`Touch.radiusY`](touch/radiusy) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the Y radius of the ellipse that most closely circumscribes the area of contact with the screen. The value is in pixels of the same scale as `screenY`.

 [`Touch.rotationAngle`](touch/rotationangle) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the angle (in degrees) that the ellipse described by radiusX and radiusY must be rotated, clockwise, to most accurately cover the area of contact between the user and the surface.

 [`Touch.force`](touch/force)<span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the amount of pressure being applied to the surface by the user, as a `float` between `0.0` (no pressure) and `1.0` (maximum pressure).

Methods
-------

*This interface has no method and no parent, and doesn't inherits or implements any method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#touch-interface">Touch Events – Level 2<br />
<span class="small">The definition of 'Touch' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Added <code>radiusX</code>, <code>radiusY</code>, <code>rotationAngle</code>, <code>force</code> properties, as well as the <code>Touch()</code> constructor.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#touch-interface">Touch Events<br />
<span class="small">The definition of 'Touch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`altitudeAngle`

No

No

No

No

No

No

No

No

No

No

10

No

`azimuthAngle`

No

No

No

No

No

No

No

No

No

No

10

No

`clientX`

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

`clientY`

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

`force`

Yes

≤79

Yes

No

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

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

`pageX`

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

`pageY`

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

`screenX`

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

`screenY`

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

`touchType`

No

No

No

No

No

No

No

No

No

No

10

No

See also
--------

-   [Touch events](touch_events)
-   [`Document.createTouch()`](document/createtouch)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch</a>
