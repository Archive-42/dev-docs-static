# KeyboardLayoutMap

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `KeyboardLayoutMap` interface of the [Keyboard API](keyboard_api) is a map-like object with functions for retrieving the string associated with specific physical keys. A list of valid keys is found in the [UI Events KeyboardEvent code Values](https://www.w3.org/TR/uievents-code/#key-alphanumeric-writing-system) specification.

## Properties

[`KeyboardLayoutMap.entries`](keyboardlayoutmap/entries) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns an array of a given object's own enumerable property `[key, value]` pairs, in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a `for-in` loop enumerates properties in the prototype chain as well).

[`KeyboardLayoutMap.keys`](keyboardlayoutmap/keys) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a new Array Iterator object that contains the keys for each index in the array.

[`KeyboardLayoutMap.size`](keyboardlayoutmap/size) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the number of elements in the `KeyboardLayoutMap` object.

[`KeyboardLayoutMap.values`](keyboardlayoutmap/values) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a new Array Iterator object that contains the values for each index in the `KeyboardLayoutMap` object.

## Methods

[`KeyboardLayoutMap.forEach()`](keyboardlayoutmap/foreach) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Executes a provided function once for each element of `KeyboardLayoutMap`.

[`KeyboardLayoutMap.get()`](keyboardlayoutmap/get) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the element with the given key from the `KeyboardLayoutMap` object.

[`KeyboardLayoutMap.has()`](keyboardlayoutmap/has) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a boolean indicating whether the `KeyboardLayoutMap` object has an element with the specified key.

## Examples

The following example demonstrates how to get the location- or layout-specific string associated with the key that corresponds to the 'W' key on an English QWERTY keyboard.

    var keyboard = navigator.keyboard;
    keyboard.getLayoutMap()
    .then(keyboardLayoutMap => {
      var upKey = keyboardLayoutMap.get('KeyW');
      window.alert('Press ' + upKey + ' to move up.');
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#keyboardlayoutmap-interface">Keyboard Map<br />
<span class="small">The definition of 'KeyboardLayoutMap' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`KeyboardLayoutMap`

69

79

No

No

55

No

No

No

No

48

No

No

`entries`

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

`forEach`

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

`has`

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

`keys`

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

`size`

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

`values`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap</a>
