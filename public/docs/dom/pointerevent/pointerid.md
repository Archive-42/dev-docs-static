# PointerEvent.pointerId

The `pointerId` read-only property of the [`PointerEvent`](../pointerevent) interface is an identifier assigned to a given pointer event. The identifier is unique, being different from the identifiers of all other active pointer events. Since the value may be randomly generated, it is not guaranteed to convey any particular meaning.

## Syntax

    var id = pointerEvent.pointerId;

### Return value

`id`  
The pointer event's unique identifier number.

## Example

The following code snippet compares a previously saved `pointerId` with the one of the `pointerdown` event that was just fired.

    let id; // Let's assume that this is a previously saved pointerId

    target.addEventListener('pointerdown', function(event) {
      // Compare previous event's ID that was cached
      // to current event's ID and handle accordingly
      if (id === event.pointerId) process_event(event);
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-pointerid">Pointer Events – Level 2<br />
<span class="small">The definition of 'pointerId' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEventInit-pointerId">Pointer Events<br />
<span class="small">The definition of 'pointerId' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pointerId`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/pointerId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/pointerId</a>
