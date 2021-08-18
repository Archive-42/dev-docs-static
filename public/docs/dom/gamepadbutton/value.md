GamepadButton.value
===================

The `GamepadButton.value` property of the [`GamepadButton`](../gamepadbutton) interface returns a double value used to represent the current state of analog buttons on many modern gamepads, such as the triggers.

The values are normalized to the range `0.0` — `1.0`, with `0.0` representing a button that is not pressed, and 1.0 representing a button that is fully pressed.

Syntax
------

        readonly    attribute double  value;

Example
-------

    var gp = navigator.getGamepads()[0];

    if(gp.buttons[0].value > 0) {
      // respond to analog button being pressed in
    } 

Value
-----

A <span class="page-not-created">`double`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepadbutton-value">Gamepad<br />
<span class="small">The definition of 'GamepadButton.value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`value`

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

See also
--------

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton/value</a>
