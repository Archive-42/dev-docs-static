# PointerEvent.isPrimary

The `isPrimary` read-only property of the [`PointerEvent`](../pointerevent) interface indicates whether or not the pointer device that created the event is the _primary_ pointer. It returns `true` if the pointer that caused the event to be fired is the primary device and returns `false` otherwise.

In a multi-pointer scenario (such as a touch screen that supports more than one touch point), this property is used to identify a _master pointer_ among the set of active pointers for each pointer type. Only a primary pointer will produce _compatibility mouse events_. Authors who desire only single-pointer interaction can achieve that by ignoring non-primary pointers.

A pointer is considered primary if the pointer represents a mouse device. A pointer representing pen input is considered the primary pen input if its `pointerdown` event was dispatched when no other active pointers representing pen input existed. A pointer representing touch input is considered the primary touch input if its `pointerdown` event was dispatched when no other active pointers representing touch input existed.

When two or more pointer device types are being used concurrently, multiple pointers (one for each [`pointerType`](pointertype)) are considered primary. For example, a touch contact and a mouse cursor moved simultaneously will produce pointers that are both considered primary. If there are multiple primary pointers, these pointers will all produce _compatibility mouse events_ (see [`Pointer_events`](../pointer_events) for more information about pointer, mouse and touch interaction).

## Syntax

    var isPrimary = pointerEvent.isPrimary;

### Return value

`isPrimary`  
Returns `true` if the pointer for this event is the primary pointer and returns `false` otherwise.

## Example

This example illustrates using the value of `isPrimary` to call the appropriate processing function.

    target.addEventListener('pointerdown', function(event) {
      if (event.isPrimary)
        process_primary_pointer(event);
      else
        process_secondary_pointer(event);
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-isprimary">Pointer Events – Level 2<br />
<span class="small">The definition of 'isPrimary' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEvent-isPrimary">Pointer Events<br />
<span class="small">The definition of 'isPrimary' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isPrimary`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/isPrimary" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/isPrimary</a>
