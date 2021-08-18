PointerEvent.tangentialPressure
===============================

The `tangentialPressure` read-only property of the [`PointerEvent`](../pointerevent) interface represents the normalized tangential pressure of the pointer input (also known as barrel pressure or [cylinder stress](https://en.wikipedia.org/wiki/Cylinder_stress)).

Syntax
------

    var tanPressure = pointerEvent.tangentialPressure;

### Return value

A `float` representing the normalized tangential pressure of the pointer input in the range `-1` to `1`, inclusive, where `0` is the neutral position of the control.

Note that some hardware may only support positive values in the range `0` to `1`. For hardware that does not support tangential pressure, the value will be `0`.

Example
-------

In this snippet, when a `pointerdown` event is fired, different functions are called depending on the value of the event's `tangentialPressure` property.

    someElement.addEventListener('pointerdown', function(event) {
      if (event.tangentialPressure == 0) {
        // No pressure
        process_no_tanPressure(event);
      } else if (event.tangentialPressure == 1) {
        // Maximum pressure
        process_max_tanPressure(event);
      } else {
        // Default
        process_tanPressure(event);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-tangentialpressure">Pointer Events – Level 2<br />
<span class="small">The definition of 'tangentialPressure' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`tangentialPressure`

58

79

59

54

No

45

13

58

58

79

54

43

13

7.0

See also
--------

-   [`Touch.force`](../touch/force)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tangentialPressure" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tangentialPressure</a>
