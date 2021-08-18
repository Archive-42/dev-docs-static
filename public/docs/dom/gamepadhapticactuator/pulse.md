# GamepadHapticActuator.pulse()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `pulse()` method of the [`GamepadHapticActuator`](../gamepadhapticactuator) interface makes the hardware pulse at a certain intensity for a specified duration.

## Syntax

    gamepadHapticActuatorInstance.pulse(value, duration).then(function(result) { ... });

### Parameters

_value_  
A double representing the intensity of the pulse. This can vary depending on the hardware type, but generally takes a value between 0.0 (no intensity) and 1.0 (full intensity).

_duration_  
A double representing the duration of the pulse, in milliseconds.

**Note**: Repeated calls to `pulse()` override the previous calls if they are still ongoing.

### Return value

A promise that resolves with a value of `true` when the pulse has successfully completed.

## Examples

TBC

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#dom-gamepadhapticactuator-pulse">Gamepad Extensions<br />
<span class="small">The definition of 'pulse()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [Gamepad API](../gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadHapticActuator/pulse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadHapticActuator/pulse</a>
