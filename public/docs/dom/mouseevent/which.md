# MouseEvent.which

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `MouseEvent.which` read-only property indicates which button was pressed on the mouse to trigger the event. The standard alternatives to this property are [`MouseEvent.button`](button) and [`MouseEvent.buttons`](buttons).

## Syntax

    var buttonPressed = instanceOfMouseEvent.which

### Return value

A number representing a given button:

- `0`: No button
- `1`: Left button
- `2`: Middle button (if present)
- `3`: Right button

For a mouse configured for left-handed use, the button actions are reversed. In this case, the values are read from right to left.

## Specifications

This is not part of any specification.

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

`which`

1

12

1

On `mousemove` events, the `which` property is incorrectly always set to `1`.

9

10.6

3.1

Yes

Yes

4

On `mousemove` events, the `which` property is incorrectly always set to `1`.

11

Yes

Yes

## See also

- [`MouseEvent`](../mouseevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/which" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/which</a>
