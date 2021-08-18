KeyboardLayoutMap.get()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `get()` method of the [`KeyboardLayoutMap`](../keyboardlayoutmap) interface returns the element with the given key. A list of valid keys is found in the [UI Events KeyboardEvent code Values](https://www.w3.org/TR/uievents-code/#key-alphanumeric-writing-system) spec.

Syntax
------

    var value = KeyboardLayoutMap.get(key)

### Parameters

key  
The key of the item to return from the map.

### Return value

The value of the specified key.

Example
-------

The following example demonstrates how to get the location- or layout-specific string associated with the key that corresponds to the 'W' key on an English QWERTY keyboard.

    var keyboard = navigator.keyboard;
    keyboard.getLayoutMap()
    .then(keyboardLayoutMap => {
      var upKey = keyboardLayoutMap.get('KeyW');
      window.alert('Press ' + upKey + ' to move up.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#keyboardlayoutmap-interface">Keyboard Map<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`get`

69

79

No

No

56

No

No

No

No

48

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/get</a>
