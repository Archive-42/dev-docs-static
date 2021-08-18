# MouseEvent.movementY

The `movementY` read-only property of the [`MouseEvent`](../mouseevent) interface provides the difference in the Y coordinate of the mouse pointer between the given event and the previous `mousemove` event. In other words, the value of the property is computed like this: `currentEvent.movementY = currentEvent.screenY - previousEvent.screenY`.

## Syntax

    var yShift = instanceOfMouseEvent.movementY;

### Return value

A number

## Example

This example logs the amount of mouse movement using [`movementX`](movementx) and `movementY`.

### HTML

    <p id="log">Move your mouse around.</p>

### JavaScript

    function logMovement(event) {
      log.innerText = `movement: ${event.movementX}, ${event.movementY}\n${log.innerText}`;
    }

    const log = document.getElementById('log');
    document.addEventListener('mousemove', logMovement);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#dom-mouseevent-movementy">Pointer Lock<br />
<span class="small">The definition of 'MouseEvent.movementY' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`movementY`

37

22-37

13

41

1-41

No

Yes

9

6-8

37

Yes-37

37

Yes-37

41

4-41

Yes

8

6-8

3.0

Yes-3.0

## See also

- [`MouseEvent.movementX`](movementx)
- [`MouseEvent`](../mouseevent)
- [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementY</a>
