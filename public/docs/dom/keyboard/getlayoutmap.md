Keyboard.getLayoutMap()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getLayoutMap()` method of the [`Keyboard`](../keyboard) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`KeyboardLayoutMap`](../keyboardlayoutmap) which is a map-like object with functions for retrieving the strings associated with specific physical keys.

Syntax
------

    var promise = Keyboard.getLayoutMap()

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`KeyboardLayoutMap`](../keyboardlayoutmap).

Example
-------

The following example demonstrates how to get the location- or layout-specific string associated with the key that corresponds to the 'W' key on an English QWERTY keyboard.

    var keyboard = navigator.keyboard;
    keyboard.getLayoutMap()
    .then(keyboardLayoutMap => {
      var upKey = keyboardLayoutMap.get('KeyW');
      window.alert('Press ' + upKey + ' to move up.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#h-keyboard-getlayoutmap">Keyboard Map<br />
<span class="small">The definition of 'getLayoutMap()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getLayoutMap`

69

79

No

No

56

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Keyboard/getLayoutMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Keyboard/getLayoutMap</a>
