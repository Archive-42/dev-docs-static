# KeyboardLayoutMap.has()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `has()` method of the [`KeyboardLayoutMap`](../keyboardlayoutmap) interface returns a boolean indicating whether the object has an element with the specified key. A list of valid keys is found in the [UI Events KeyboardEvent code Values](https://www.w3.org/TR/uievents-code/#key-alphanumeric-writing-system) spec.

## Syntax

    var aBoolean = KeyboardLayoutMap.has(key)

### Parameters

key  
The key of an element to search for in the map.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the specified key was found.

## Example

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#keyboardlayoutmap-interface">Keyboard Map<br />
<span class="small">The definition of 'has()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/has</a>
