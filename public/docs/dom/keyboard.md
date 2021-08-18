# Keyboard

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Keyboard` interface of the [Keyboard API](keyboard_api) provides functions that retrieve keyboard layout maps and toggle capturing of key presses from the physical keyboard.

A list of valid code values is found in the [UI Events KeyboardEvent code Values](https://www.w3.org/TR/uievents-code/#key-alphanumeric-writing-system) spec.

## Properties

None.

## Methods

[`Keyboard.getLayoutMap()`](keyboard/getlayoutmap) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`KeyboardLayoutMap`](keyboardlayoutmap) which is a map-like object with functions for retrieving the strings associated with specific physical keys.

[`Keyboard.lock()`](keyboard/lock) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) after enabling the capture of keypresses for any or all of the keys on the physical keyboard.

[`Keyboard.unlock()`](keyboard/unlock) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Unlocks all keys captured by the `lock()` method and returns synchronously.

## Example

The following example demonstrates how to get the location- or layout-specific string associated with the key that corresponds to the 'W' key on an English QWERTY keyboard.

    if (navigator.keyboard) {
      var keyboard = navigator.keyboard;
      keyboard.getLayoutMap()
      .then(keyboardLayoutMap => {
        var upKey = keyboardLayoutMap.get('KeyW');
        window.alert('Press ' + upKey + ' to move up.');
      });
    } else {
      // Do something else.
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/keyboard-map/#keyboard-interface">Keyboard Map<br />
<span class="small">The definition of 'Keyboard' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://wicg.github.io/keyboard-lock/#keyboard-interface">Keyboard Lock<br />
<span class="small">The definition of 'Keyboard' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds <code>lock()</code> and <code>unlock()</code>.</td></tr></tbody></table>

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

`Keyboard`

68

79

No

No

55

No

No

No

No

No

No

No

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

`lock`

68

79

No

No

55

No

No

No

No

No

No

No

`unlock`

68

79

No

No

55

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Keyboard" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Keyboard</a>
