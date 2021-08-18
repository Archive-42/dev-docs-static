# GamepadEvent

The GamepadEvent interface of the Gamepad API contains references to gamepads connected to the system, which is what the gamepad events <span class="page-not-created">`Window.gamepadconnected`</span> and <span class="page-not-created">`Window.gamepaddisconnected`</span> are fired in response to.

## Constructor

[`GamepadEvent()`](gamepadevent/gamepadevent)  
Returns a new `GamepadEvent` object.

## Properties

[`GamepadEvent.gamepad`](gamepadevent/gamepad) <span class="badge inline readonly">Read only </span>  
Returns a [`Gamepad`](gamepad) object, providing access to the associated gamepad data for the event fired.

## Examples

The gamepad property being called on a fired <span class="page-not-created">`Window.gamepadconnected`</span> event.

    window.addEventListener("gamepadconnected", function(e) {
      console.log("Gamepad connected at index %d: %s. %d buttons, %d axes.",
      e.gamepad.index, e.gamepad.id,
      e.gamepad.buttons.length, e.gamepad.axes.length);
    });

And on a <span class="page-not-created">`Window.gamepaddisconnected`</span> event.

    window.addEventListener("gamepaddisconnected", function(e) {
      console.log("Gamepad disconnected from index %d: %s",
      e.gamepad.index, e.gamepad.id);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#gamepadevent-interface">Gamepad<br />
<span class="small">The definition of 'GamepadEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`GamepadEvent`

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

`GamepadEvent`

35

12

29

No

22

10.1

37

35

32

22

10.3

3.0

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

[Using the Gamepad API](gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadEvent</a>
