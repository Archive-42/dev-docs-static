# MouseEvent.movementX

The `movementX` read-only property of the [`MouseEvent`](../mouseevent) interface provides the difference in the X coordinate of the mouse pointer between the given event and the previous `mousemove` event. In other words, the value of the property is computed like this: `currentEvent.movementX = currentEvent.screenX - previousEvent.screenX`.

## Syntax

    var xShift = instanceOfMouseEvent.movementX;

### Return value

A number

## Example

This example logs the amount of mouse movement using `movementX` and [`movementY`](movementy).

### HTML

    <p id="log">Move your mouse around.</p>

### JavaScript

    function logMovement(event) {
      log.insertAdjacentHTML('afterbegin', `movement: ${event.movementX}, ${event.movementY}<br>`);
      while (log.childNodes.length > 128) log.lastChild.remove()
    }

    const log = document.getElementById('log');
    document.addEventListener('mousemove', logMovement);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#dom-mouseevent-movementx">Pointer Lock<br />
<span class="small">The definition of 'MouseEvent.movementX' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`movementX`

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

- [`MouseEvent.movementY`](movementy)
- [`MouseEvent`](../mouseevent)
- [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementX</a>
