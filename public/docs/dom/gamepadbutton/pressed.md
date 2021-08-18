# GamepadButton.pressed

The `GamepadButton.pressed` property of the [`GamepadButton`](../gamepadbutton) interface returns a `boolean` indicating whether the button is currently pressed (`true`) or unpressed (`false`).

## Syntax

    var isPressed = navigator.getGamepads()[0].pressed;

## Example

    var gp = navigator.getGamepads()[0]; // Get the first gamepad object

    if(gp.buttons[0].pressed == true) {
      // respond to button being pressed
    }

## Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepadbutton-pressed">Gamepad<br />
<span class="small">The definition of 'GamepadButton.pressed' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`pressed`

35

21-34

12

29

No

22

15-21

10.1

No

Yes

32

22

14-21

10.3

Yes

## See also

- [Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton/pressed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton/pressed</a>
