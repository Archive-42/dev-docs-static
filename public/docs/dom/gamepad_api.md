Gamepad API
===========

The **Gamepad API** is a way for developers to access and respond to signals from gamepads and other game controllers in a simple, consistent way. It contains three interfaces, two events and one specialist function, to respond to gamepads being connected and disconnected, and to access other information about the gamepads themselves, and what buttons and other controls are currently being pressed.

Interfaces
----------

[`Gamepad`](gamepad)  
Represents a gamepad/controller connected to the computer.

[`GamepadButton`](gamepadbutton)  
Represents a button on one of the connected controllers.

[`GamepadEvent`](gamepadevent)  
The event object representing events fired that are related to gamepads.

### Experimental Gamepad extensions

[`GamepadHapticActuator`](gamepadhapticactuator)  
Represents hardware in the controller designed to provide haptic feedback to the user (if available), most commonly vibration hardware.

[`GamepadPose`](gamepadpose)  
Represents the pose of a controller (e.g. position and orientation in 3D space) in the case of a [WebVR](webvr_api) controller. This is *not* used by the newer [WebXR](webxr_device_api) standard.

See also the [extensions to the Gamepad interface](gamepad#experimental_extensions_to_gamepad), for features that allow you to access the above information.

### Extensions to other interfaces

#### Navigator

[`Navigator.getGamepads()`](navigator/getgamepads)  
An extension to the [`Navigator`](navigator) object that returns an array of [`Gamepad`](gamepad) objects, one for each connected gamepad.

#### Window events

[`Window.ongamepadconnected`](window/ongamepadconnected)  
Represents an event handler that will run when a gamepad is connected (when the `gamepadconnected` event fires).

[`Window.ongamepaddisconnected`](window/ongamepaddisconnected)  
Represents an event handler that will run when a gamepad is disconnected (when the `gamepaddisconnected` event fires).

Tutorials and guides
--------------------

-   [Using the Gamepad API](gamepad_api/using_the_gamepad_api)
-   [Implementing controls using the Gamepad API](https://developer.mozilla.org/en-US/docs/Games/Techniques/Controls_Gamepad_API)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html">Gamepad Extensions</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines the <a href="#experimental_gamepad_extensions">Experimental Gamepad extensions</a>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/gamepad/">Gamepad<br />
<span class="small">The definition of 'The Gamepad API specification' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Gamepad_API`

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

See also
--------

-   [The Gamepad API](https://hacks.mozilla.org/2013/12/the-gamepad-api/) by Ted Mielczarek and Robert Nyman
-   [Simple API demo page](https://luser.github.io/gamepadtest/) ([source](https://github.com/luser/gamepadtest))

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API</a>
