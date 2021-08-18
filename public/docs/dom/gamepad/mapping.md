Gamepad.mapping
===============

The `Gamepad.mapping` property of the [`Gamepad`](../gamepad) interface returns a string indicating whether the browser has remapped the controls on the device to a known layout.

Currently there is only one supported known layout–the [standard gamepad](https://dvcs.w3.org/hg/gamepad/raw-file/default/gamepad.html#remapping). If the browser is able to map controls on the device to that layout the `mapping` property will be set to the string `standard`.

Syntax
------

    readonly    attribute DOMString           mapping;

Example
-------

    var gp = navigator.getGamepads()[0];
    console.log(gp.mapping);

Value
-----

A <span class="page-not-created">`string`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-mapping">Gamepad<br />
<span class="small">The definition of 'Gamepad.mapping' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/mapping" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/mapping</a>
