Gamepad.buttons
===============

The `Gamepad.buttons` property of the [`Gamepad`](../gamepad) interface returns an array of [`gamepadButton`](../gamepadbutton) objects representing the buttons present on the device.

Each entry in the array is 0 if the button is not pressed, and non-zero (typically 1.0) if the button is pressed. Each [`gamepadButton`](../gamepadbutton) object has two properties: `pressed` and `value`:

-   The `pressed` property is a boolean indicating whether the button is currently pressed (`true`) or unpressed (`false`).
-   The `value` property is a floating point value used to enable representing analog buttons, such as the triggers on many modern gamepads. The values are normalized to the range 0.0 – 1.0, with 0.0 representing a button that is not pressed, and 1.0 representing a button that is fully pressed.

Syntax
------

    readonly    attribute GamepadButton[]     buttons;

Example
-------

The following code is taken from my Gamepad API button demo (you can [view the demo live](https://chrisdavidmills.github.io/gamepad-buttons/), and [find the source code](https://github.com/chrisdavidmills/gamepad-buttons/tree/master) on Github.) Note the code fork — in Chrome [`Navigator.getGamepads`](../navigator/getgamepads) needs a `webkit` prefix and the button values are stores as an array of double values, whereas in Firefox [`Navigator.getGamepads`](../navigator/getgamepads) doesn't need a prefix, and the button values are stored as an array of [`GamepadButton`](../gamepadbutton) objects; it is the [`GamepadButton.value`](../gamepadbutton/value) or [`GamepadButton.pressed`](../gamepadbutton/pressed) properties of these we need to access, depending on what type of buttons they are. In this simple example I've just allowed either.

    function gameLoop() {
      if(navigator.webkitGetGamepads) {
        var gp = navigator.webkitGetGamepads()[0];

        if(gp.buttons[0] == 1) {
          b--;
        } else if(gp.buttons[1] == 1) {
          a++;
        } else if(gp.buttons[2] == 1) {
          b++;
        } else if(gp.buttons[3] == 1) {
          a--;
        }
      } else {
        var gp = navigator.getGamepads()[0];

        if(gp.buttons[0].value > 0 || gp.buttons[0].pressed == true) {
          b--;
        } else if(gp.buttons[1].value > 0 || gp.buttons[1].pressed == true) {
          a++;
        } else if(gp.buttons[2].value > 0 || gp.buttons[2].pressed == true) {
          b++;
        } else if(gp.buttons[3].value > 0 || gp.buttons[3].pressed == true) {
          a--;
        }
      }

      ball.style.left = a*2 + "px";
      ball.style.top = b*2 + "px";

      var start = rAF(gameLoop);
    };

Value
-----

An array of [`gamepadButton`](../gamepadbutton) objects.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-buttons">Gamepad<br />
<span class="small">The definition of 'Gamepad.buttons' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`buttons`

35

21-34

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

See also
--------

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/buttons" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/buttons</a>
