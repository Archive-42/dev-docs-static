# Gamepad

The `Gamepad` interface of the [Gamepad API](gamepad_api) defines an individual gamepad or other controller, allowing access to information such as button presses, axis positions, and id.

A Gamepad object can be returned in one of two ways: via the `gamepad` property of the `gamepadconnected` and `gamepaddisconnected` events, or by grabbing any position in the array returned by the [`Navigator.getGamepads()`](navigator/getgamepads) method.

## Properties

[`Gamepad.axes`](gamepad/axes) <span class="badge inline readonly">Read only </span>  
An array representing the controls with axes present on the device (e.g. analog thumb sticks).

[`Gamepad.buttons`](gamepad/buttons) <span class="badge inline readonly">Read only </span>  
An array of [`gamepadButton`](gamepadbutton) objects representing the buttons present on the device.

[`Gamepad.connected`](gamepad/connected) <span class="badge inline readonly">Read only </span>  
A boolean indicating whether the gamepad is still connected to the system.

[`Gamepad.displayId`](gamepad/displayid) <span class="badge inline readonly">Read only </span>  
Returns the [`VRDisplay.displayId`](vrdisplay/displayid) of an associated [`VRDisplay`](vrdisplay) (if relevant) — the `VRDisplay` that the gamepad is controlling the displayed scene of.

[`Gamepad.id`](gamepad/id) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing identifying information about the controller.

[`Gamepad.index`](gamepad/index) <span class="badge inline readonly">Read only </span>  
An integer that is auto-incremented to be unique for each device currently connected to the system.

[`Gamepad.mapping`](gamepad/mapping) <span class="badge inline readonly">Read only </span>  
A string indicating whether the browser has remapped the controls on the device to a known layout.

[`Gamepad.timestamp`](gamepad/timestamp) <span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the last time the data for this gamepad was updated.

### Experimental extensions to Gamepad

The following interfaces are defined in the [Gamepad Extensions](https://w3c.github.io/gamepad/extensions.html) specification, and provide access to experimental features like haptic feedback and WebVR controller pose information.

[`Gamepad.hand`](gamepad/hand) <span class="badge inline readonly">Read only </span>  
An enum defining what hand the controller is being held in, or is most likely to be held in.

[`Gamepad.hapticActuators`](gamepad/hapticactuators) <span class="badge inline readonly">Read only </span>  
An array containing [`GamepadHapticActuator`](gamepadhapticactuator) objects, each of which represents haptic feedback hardware available on the controller.

[`Gamepad.pose`](gamepad/pose) <span class="badge inline readonly">Read only </span>  
A [`GamepadPose`](gamepadpose) object representing the pose information associated with a WebVR controller (e.g. its position and orientation in 3D space).

## Example

    window.addEventListener("gamepadconnected", function(e) {
      console.log("Gamepad connected at index %d: %s. %d buttons, %d axes.",
      e.gamepad.index, e.gamepad.id,
      e.gamepad.buttons.length, e.gamepad.axes.length);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#gamepad-interface">Gamepad<br />
<span class="small">The definition of 'Gamepad' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#gamepad-getvrdisplays-attribute">WebVR 1.1<br />
<span class="small">The definition of 'displayId' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Defines the <a href="gamepad/displayid"><code>Gamepad.displayId</code></a> property.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#partial-gamepad-interface">Gamepad Extensions<br />
<span class="small">The definition of 'Gamepad extensions' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines the <a href="#experimental_extensions_to_gamepad">Experimental extensions to Gamepad</a></td></tr></tbody></table>

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

`Gamepad`

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

`axes`

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

`displayId`

55-80

Only works on desktop in an [experimental version of Chrome](https://webvr.info/get-chrome/) (other builds won't return any devices when `Navigator.getVRDisplays()` is invoked).

79-80

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

55-80

Currently supported only by Google Daydream.

55

?

No

6.0-13.0

Currently supported only by Google Daydream.

`hand`

No

15-79

55

No

No

No

No

No

55

No

No

No

`hapticActuators`

No

15-79

55

No

No

No

No

No

55

No

No

No

`id`

35

21-34

12

29

No

22

15-21

No

No

35

25-34

32

22

14-21

No

4.0

2.0-3.0

`index`

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

`mapping`

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

`pose`

No

15-79

55

No

No

No

No

No

55

No

No

No

`timestamp`

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

`vibrationActuator`

68

79

No

No

55

No

No

68

No

48

No

10.0

## See also

- [Using the Gamepad API](gamepad_api/using_the_gamepad_api)
- [Gamepad API](gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad</a>
