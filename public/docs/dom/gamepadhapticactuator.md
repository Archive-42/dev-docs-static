GamepadHapticActuator
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `GamepadHapticActuator` interface of the [Gamepad API](gamepad_api) represents hardware in the controller designed to provide haptic feedback to the user (if available), most commonly vibration hardware.

This interface is accessible through the [`Gamepad.hapticActuators`](gamepad/hapticactuators) property.

Properties
----------

 [`GamepadHapticActuator.type`](gamepadhapticactuator/type) <span class="badge inline readonly">Read only </span>   
Returns an enum representing the type of the haptic hardware.

Methods
-------

 [`GamepadHapticActuator.pulse()`](gamepadhapticactuator/pulse) <span class="badge inline readonly">Read only </span>   
Makes the hardware pulse at a certain intensity for a specified duration.

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#gamepadhapticactuator-interface">Gamepad Extensions<br />
<span class="small">The definition of 'GamepadHapticActuator' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`GamepadHapticActuator`

68

15

55

No

55

No

No

68

55

48

No

10.0

`playEffect`

68

15

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

`pulse`

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

`reset`

68

15

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

`type`

68

15

55

No

55

No

No

68

55

48

No

10.0

See also
--------

-   [Gamepad API](gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadHapticActuator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadHapticActuator</a>
