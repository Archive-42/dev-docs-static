# PointerEvent.tiltY

The `tiltY` read-only property of the [`PointerEvent`](../pointerevent) interface is the angle (in degrees) between the _X-Z plane_ of the pointer and the screen. This property is typically only useful for a pen/stylus pointer type.

For an illustration of this property, see [Figure 3 in the specification](https://w3c.github.io/pointerevents/#dom-pointerevent-tilty).

## Syntax

    var tiltY = pointerEvent.tiltY;

### Return value

`tiltY`  
The angle in degrees between the X-Z plane of the pointer (stylus) and the screen. The range of values is `-90` to `90`, inclusive, where a positive value is a tilt towards the user. For devices that do not support this property, the value is `0`.

## Example

This example illustrates simple accessing of the [`tiltX`](tiltx) and `tiltY` properties.

    someElement.addEventListener("pointerdown", function(event) {
      process_tilt(event.tiltX, event.tiltY);
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-tilty">Pointer Events – Level 2<br />
<span class="small">The definition of 'tiltY' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEventInit-tiltY">Pointer Events<br />
<span class="small">The definition of 'tiltY' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`tiltY`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tiltY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tiltY</a>
