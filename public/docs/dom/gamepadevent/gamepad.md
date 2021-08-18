# GamepadEvent.gamepad

The `GamepadEvent.gamepad` property of the **[`GamepadEvent`](../gamepadevent) interface** returns a [`Gamepad`](../gamepad) object, providing access to the associated gamepad data for fired `gamepadconnected` and `gamepaddisconnected` events.

## Syntax

    readonly    attribute Gamepad gamepad;

## Example

The `gamepad` property being called on a fired <span class="page-not-created">`Window.gamepadconnected`</span> event.

    window.addEventListener("gamepadconnected", function(e) {
      console.log("Gamepad connected at index %d: %s. %d buttons, %d axes.",
      e.gamepad.index, e.gamepad.id,
      e.gamepad.buttons.length, e.gamepad.axes.length);
    });

## Value

A [`Gamepad`](../gamepad) object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepadevent-gamepad">Gamepad<br />
<span class="small">The definition of 'GamepadEvent.gamepad' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`gamepad`

35

21-34

12

29

No

22

15-21

10.1

37

35

25-34

32

22

14-21

10.3

Yes

## See also

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadEvent/gamepad" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadEvent/gamepad</a>
