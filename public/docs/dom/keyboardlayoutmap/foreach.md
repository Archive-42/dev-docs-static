KeyboardLayoutMap.forEach()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `forEach()` method of the [`KeyboardLayoutMap`](../keyboardlayoutmap) interface executes a provided function once for each element of the map.

Syntax
------

    KeyboardLayoutMap.forEach(function callback(currentValue[, index[, array]]) {
        //your iterator
    }[, thisArg]);

### Parameters

`callback`  
The function to execute for each element, taking three arguments:

`currentValue`  
The value of the current element being processed.

 `index` <span class="badge inline optional">Optional</span>   
The index of the current element being processed.

 `array` <span class="badge inline optional">Optional</span>   
The KeyboardLayoutMap that `forEach()` is being called on.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` (i.e the reference `Object`) when executing `callback`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#keyboardlayoutmap-interface">Keyboard Map<br />
<span class="small">The definition of 'forEach()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap/forEach</a>
