PointerEvent.pressure
=====================

The `pressure` read-only property of the [`PointerEvent`](../pointerevent) interface indicates the normalized pressure of the pointer input.

Syntax
------

    var pressure = pointerEvent.pressure;

### Return value

`pressure`  
The normalized pressure of the pointer input in the range of `0` to `1`, inclusive, where `0` and `1` represent the minimum and maximum pressure the hardware is capable of detecting, respectively. For hardware that does not support pressure, such as a mouse, the value is `0.5` when the pointer is active buttons state and `0` otherwise.

Example
-------

In this snippet, when a `pointerdown` event is fired, different functions are called depending on the value of the event's `pressure` property.

    someElement.addEventListener('pointerdown', function(event) {
      if (event.pressure == 0) {
        // No pressure
        process_no_pressure(event);
      } else if (event.pressure == 1) {
        // Maximum pressure
        process_max_pressure(event);
      } else {
        // Default
        process_pressure(event);
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-pressure">Pointer Events – Level 2<br />
<span class="small">The definition of 'pressure' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEventInit-pressure">Pointer Events<br />
<span class="small">The definition of 'pressure' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pressure`

55

12

59

41

11

10

Returns 0 instead of 0.5 on hardware that doesn't support pressure.

42

13

55

55

79

41

42

13

6.0

See also
--------

-   [`Touch.force`](../touch/force)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/pressure" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/pressure</a>
