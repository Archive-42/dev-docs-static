PointerEvent.twist
==================

The `twist` read-only property of the [`PointerEvent`](../pointerevent) interface represents the clockwise rotation of the pointer (e.g., pen stylus) around its major axis, in degrees.

Syntax
------

    var twist = pointerEvent.twist;

### Return value

A `long` value representing the amount of twist, in degrees, applied to the transducer (pointer). The value is in the range `0` to `359`, inclusive. For devices that do not report `twist`, the value is `0`.

Example
-------

When a `pointerdown` event is fired, different functions are called depending on the value of the event's `twist` property.

    someElement.addEventListener('pointerdown', function(event) {
      if (event.twist == 0) {
        // No twist
        process_no_twist(event);
      } else {
        // Default
        process_twist(event);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-twist">Pointer Events – Level 2<br />
<span class="small">The definition of 'twist' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`twist`

58

18

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/twist" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/twist</a>
