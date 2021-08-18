Navigator.getGamepads()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Navigator.getGamepads()` method returns an array of [`Gamepad`](../gamepad) objects, one for each gamepad connected to the device.

Elements in the array may be `null` if a gamepad disconnects during a session, so that the remaining gamepads retain the same index.

Syntax
------

     var gamepads = navigator.getGamepads();

Example
-------

    window.addEventListener("gamepadconnected", function(e) {
      var gp = navigator.getGamepads()[e.gamepad.index];
      console.log(
        "Gamepad connected at index %d: %s. %d buttons, %d axes.",
        gp.index, gp.id, gp.buttons.length, gp.axes.length
      );
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/">Gamepad<br />
<span class="small">The definition of 'The Gamepad API specification' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getGamepads`

35

21

12

29

No

22

15

10.1

37

≤37

35

25

No

22

14

10.3

3.0

1.5

See also
--------

-   [Using the Gamepad API](../gamepad_api/using_the_gamepad_api)
-   [Gamepad API](../gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getGamepads" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getGamepads</a>
