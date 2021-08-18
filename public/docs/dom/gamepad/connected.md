# Gamepad.connected

The `Gamepad.connected` property of the [`Gamepad`](../gamepad) interface returns a boolean indicating whether the gamepad is still connected to the system.

If the gamepad is connected, the value is `true`; if not, it is `false`.

## Syntax

     readonly    attribute boolean             connected;

## Example

    var gp = navigator.getGamepads()[0];
    console.log(gp.connected);

## Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-connected">Gamepad<br />
<span class="small">The definition of 'Gamepad.connected' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`connected`

35

25-34

12

29

No

22

15-21

10.1

No

35

25-34

32

22

14-21

10.3

4.0

2.0-3.0

## See also

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/connected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/connected</a>
