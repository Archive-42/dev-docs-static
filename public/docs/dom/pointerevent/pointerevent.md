# PointerEvent.PointerEvent()

The `PointerEvent()` constructor creates a new synthetic and untrusted [`PointerEvent`](../pointerevent) object instance.

## Syntax

     event = new PointerEvent(type, PointerEventInit);

### Arguments

_type_  
Is a [`DOMString`](../domstring) representing the name of the event (see [PointerEvent event types](../pointerevent#pointer_event_types)).

_PointerEventInit_<span class="badge inline optional">Optional</span>  
Is a `PointerEventInit` dictionary, having the following fields:

- `pointerId` — optional and defaulting to `0`, of type `long`, that sets the value of the instance's [`PointerEvent.pointerId`](pointerid).
- `width` — optional and defaulting to `1`, of type `double`, that sets the value of the instance's [`PointerEvent.width`](width).
- `height` — optional and defaulting to `1`, of type `double`, that sets the value of the instance's [`PointerEvent.height`](height).
- `pressure` — optional and defaulting to `0`, of type `float`, that sets the value of the instance's [`PointerEvent.pressure`](pressure).
- `tangentialPressure` — optional and defaulting to `0`, of type `float`, that sets the value of the instance's [`PointerEvent.tangentialPressure`](tangentialpressure).
- `tiltX` — optional and defaulting to `0`, of type `long`, that sets the value of the instance's [`PointerEvent.tiltX`](tiltx).
- `tiltY` — optional and defaulting to `0`, of type `long`, that sets the value of the instance's [`PointerEvent.tiltY`](tilty).
- `twist` — optional and defaulting to `0`, of type `long`, that sets the value of the instance's [`PointerEvent.twist`](twist).
- `pointerType` — optional and defaulting to `""`, of type [`DOMString`](../domstring), that sets the value of the instance's [`PointerEvent.pointerType`](pointertype).
- `isPrimary` — optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of the instance's [`PointerEvent.isPrimary`](isprimary).

**Note**: The `PointerEventInit` dictionary also accepts fields from the [`MouseEvent`](../mouseevent/mouseevent), [`UIEventInit`](../uievent/uievent) and [`EventInit`](../event/event) dictionaries.

## Example

    var moveEvent = new PointerEvent("pointermove");

    var downEvent = new PointerEvent("pointerdown",
       {pointerId: 1,
        bubbles: true,
        cancelable: true,
        pointerType: "touch",
        width: 100,
        height: 100,
        isPrimary: true
       });

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

`PointerEvent`

55

12

59

41

11

10

See [MSDN Pointer events updates](https://msdn.microsoft.com/library/dn304886).

42

13

55

55

79

41

42

13

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/PointerEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/PointerEvent</a>
