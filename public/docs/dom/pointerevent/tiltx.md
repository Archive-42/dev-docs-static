# PointerEvent.tiltX

The `tiltX` read-only property of the [`PointerEvent`](../pointerevent) interface is the angle (in degrees) between the _Y-Z plane_ of the pointer and the screen. This property is typically only useful for a pen/stylus pointer type.

For an illustration of this property see [Figure 2 in the specification](https://w3c.github.io/pointerevents/#dom-pointerevent-tiltx).

## Syntax

    var tiltX = pointerEvent.tiltX;

### Return value

`tiltX`  
The angle in degrees between the Y-Z plane of the pointer (stylus) and the screen. The range of values is `-90` to `90`, inclusive, where a positive value is a tilt to the right. For devices that do not support this property, the value is `0`.

## Example

This example illustrates simple accessing of the `tiltX` and [`tiltY`](tilty) properties.

    someElement.addEventListener("pointerdown", function(event) {
      process_tilt(event.tiltX, event.tiltY);
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-tiltx">Pointer Events – Level 2<br />
<span class="small">The definition of 'tiltX' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEventInit-tiltX">Pointer Events<br />
<span class="small">The definition of 'tiltX' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`tiltX`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tiltX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/tiltX</a>
