# Clipboard.writeText()

The [`Clipboard`](../clipboard) interface's `writeText()` property writes the specified text string to the system clipboard. Text may be read back using either [`read()`](read) or [`readText()`](readtext).

The `"clipboard-write"` permission of the [Permissions API](../permissions_api), is granted automatically to pages when they are in the active tab.

## Syntax

    var promise = navigator.clipboard.writeText(newClipText)

### Parameters

`newClipText`  
The [`DOMString`](../domstring) to be written to the clipboard.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once the clipboard's contents have been updated. The promise is rejected if the caller does not have permission to write to the clipboard.

## Example

This example sets the clipboard's contents to the string "&lt;empty clipboard&gt;".

    navigator.clipboard.writeText("<empty clipboard>").then(function() {
      /* clipboard successfully set */
    }, function() {
      /* clipboard write failed */
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboard-writetext">Clipboard API and events<br />
<span class="small">The definition of 'writeText()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`writeText`

66

79

63

Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `"clipboardWrite"` permission can write to the clipboard at any time.

No

53

13.1

66

66

63

Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `"clipboardWrite"` permission can write to the clipboard at any time.

47

13.4

9.0

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/writeText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/writeText</a>
