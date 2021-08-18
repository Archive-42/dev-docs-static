# MediaKeyStatusMap.forEach()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `forEach` property of the [`MediaKeyStatusMap`](../mediakeystatusmap) interface calls callback once for each key-value pair in the status map, in insertion order. If an argument is present it will be passed to the callback.

## Syntax

    mediaKeyStatusMap.forEach(callback[, thisArg])

### Parameters

`callback`  
Function to execute for each element, taking three arguments:

`currentValue`  
The current element being processed in the array.

`index`  
The index of the current element being processed in the array.

`array`  
Which array `forEach()` is being applied to.

`thisArg Optional`  
Value used as `this` when executing `callback`.

### Returns

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/">Encrypted Media Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`forEach`

42

13

47

No

29

12.1

43

42

47

29

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap/forEach</a>
