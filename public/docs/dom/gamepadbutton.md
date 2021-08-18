GamepadButton
=============

The `GamepadButton` interface defines an individual button of a gamepad or other controller, allowing access to the current state of different types of buttons available on the control device.

A `GamepadButton` object is returned by querying any value of the array returned by the `buttons` property of the [`Gamepad`](gamepad) interface.

**Note**: This is the case in Firefox Gecko 28 and later; Chrome and earlier Firefox versions still return an array of double values when this property is accessed.

Properties
----------

 [`GamepadButton.value`](gamepadbutton/value) <span class="badge inline readonly">Read only </span>   
A double value used to represent the current state of analog buttons, such as the triggers on many modern gamepads. The values are normalized to the range 0.0 —1.0, with 0.0 representing a button that is not pressed, and 1.0 representing a button that is fully pressed.

 [`GamepadButton.pressed`](gamepadbutton/pressed) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether the button is currently pressed (`true`) or unpressed (`false`).

Example
-------

The following code is taken from my Gamepad API button demo (you can [view the demo live](https://chrisdavidmills.github.io/gamepad-buttons/), and [find the source code](https://github.com/chrisdavidmills/gamepad-buttons/tree/master) on Github.) Note the code fork — in Chrome [`Navigator.getGamepads`](navigator/getgamepads) needs a `webkit` prefix and the button values are stored as an array of double values, whereas in Firefox [`Navigator.getGamepads`](navigator/getgamepads) doesn't need a prefix, and the button values are stored as an array of [`GamepadButton`](gamepadbutton) objects; it is the [`GamepadButton.value`](gamepadbutton/value) or [`GamepadButton.pressed`](gamepadbutton/pressed) properties of these we need to access, depending on what type of buttons they are. In this simple example I've just allowed either.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#gamepadbutton-interface">Gamepad<br />
<span class="small">The definition of 'GamepadButton' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`GamepadButton`

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

`touched`

73

15

55

No

60

10.1

No

73

55

52

10.3

11.0

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

[Using the Gamepad API](gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadButton</a>
