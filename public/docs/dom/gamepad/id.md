# Gamepad.id

The `Gamepad.id` property of the [`Gamepad`](../gamepad) interface returns a string containing some information about the controller.

The exact syntax is not strictly specified, but in Firefox it will contain three pieces of information separated by dashes (`-`):

- Two 4-digit hexadecimal strings containing the USB vendor and product id of the controller
- The name of the controller as provided by the driver.

For example, a PS2 controller returned **810-3-USB Gamepad**.

This information is intended to allow you to find a mapping for the controls on the device as well as display useful feedback to the user.

## Syntax

    readonly    attribute DOMString           id;

## Example

    window.addEventListener("gamepadconnected", function() {
      var gp = navigator.getGamepads()[0];
      gamepadInfo.innerHTML = "Gamepad connected at index " + gp.index + ": " + gp.id + ".";
    });

## Value

A <span class="page-not-created">`string`</span>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-id">Gamepad<br />
<span class="small">The definition of 'Gamepad.id' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/id</a>
