Gamepad.index
=============

The `Gamepad.index` property of the [`Gamepad`](../gamepad) interface returns an integer that is auto-incremented to be unique for each device currently connected to the system.

This can be used to distinguish multiple controllers; a gamepad that is disconnected and reconnected will retain the same index.

Syntax
------

    readonly    attribute long                index;

Example
-------

    window.addEventListener("gamepadconnected", function() {
      var gp = navigator.getGamepads()[0];
      gamepadInfo.innerHTML = "Gamepad connected at index " + gp.index + ": " + gp.id + ".";
    });

### Value

A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-index">Gamepad<br />
<span class="small">The definition of 'Gamepad.index' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/index</a>
