# Keyboard.lock()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `lock()` method of the [`Keyboard`](../keyboard) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) after enabling the capture of keypresses for any or all of the keys on the physical keyboard. This method can only capture keys that are granted access by the underlying operating system.

## Syntax

    var promise = Keyboard.lock([keyCodes[]])

### Parameters

`keyCodes` <span class="badge inline optional">Optional</span>  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of one or more key codes to lock. If no keycodes are provided all keys will be locked. A list of valid code values is found in the [UI Events KeyboardEvent code Values](https://www.w3.org/TR/uievents-code/#key-alphanumeric-writing-system) spec.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Examples

### Capturing all keys

The following example captures all keypresses.

    navigator.keyboard.lock();

### Capturing specific keys

The following example captures the "W", "A", "S", and "D" keys. It captures these keys regardless of which modifiers are used with the key press. Assuming a standard US QWERTY layout, registering `"KeyW"` ensures that "W", Shift+"W", Control+"W", Control+Shift+"W", and all other key modifier combinations with "W" are sent to the app. The same applies to for `"KeyA"`, `"KeyS"` and `"KeyD"`.

    navigator.keyboard.lock(["KeyW", "KeyA", "KeyS", "KeyD"]);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span> <a href="https://wicg.github.io/keyboard-lock/#h-keyboard-lock">Keyboard Lock<br />
<span class="small">The definition of 'lock()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Keyboard/lock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Keyboard/lock</a>
