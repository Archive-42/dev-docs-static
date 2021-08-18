Window.ongamepadconnected
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ongamepadconnected` property of the [`Window`](../window) interface represents an event handler that will run when a gamepad is connected (when the `gamepadconnected` event fires).

The event object is of type [`GamepadEvent`](../gamepadevent).

Syntax
------

    window.ongamepadconnected = function() { ... };

Examples
--------

    window.ongamepadconnected = function(event) {
      // All buttons and axes values can be accessed through
      event.gamepad;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#event-gamepadconnected">Gamepad<br />
<span class="small">The definition of 'gamepadconnected event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ongamepadconnected`

35

21-35

≤18

29

No

22

15-22

10.1

No

35

25-35

32

22

14-22

No

3.0

1.5-3.0

See also
--------

-   [The Gamepad API](https://hacks.mozilla.org/2013/12/the-gamepad-api/) by Ted Mielczarek and Robert Nyman
-   [Simple API demo page](https://luser.github.io/gamepadtest/) ([source](https://github.com/luser/gamepadtest))

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/ongamepadconnected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/ongamepadconnected</a>
