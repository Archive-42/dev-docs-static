Window: gamepadconnected event
==============================

The `gamepadconnected` event is fired when the browser detects that a gamepad has been connected or the first time a button/axis of the gamepad is used.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../gamepadevent"><code>GamepadEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ongamepadconnected"><code>ongamepadconnected</code></a></td></tr></tbody></table>

Examples
--------

    window.addEventListener('gamepadconnected', event => {

        // All buttons and axes values can be accessed through
        event.gamepad;

    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#the-gamepadconnected-event">Gamepad</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`gamepadconnected_event`

35

21-35

≤18

29

No

22

15-22

10.1

37

37

32

Yes

No

3.0

See also
--------

-   [gamepaddisconnected](gamepaddisconnected_event)
-   [Using Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/gamepadconnected_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/gamepadconnected_event</a>
