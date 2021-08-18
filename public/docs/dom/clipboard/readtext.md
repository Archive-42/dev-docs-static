# Clipboard.readText()

The **[`Clipboard`](../clipboard)** interface's `readText()` method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with a copy of the textual contents of the system clipboard.. The `"clipboard-read"` permission of the [Permissions API](../permissions_api) must be granted before you can read data from the clipboard.

## Syntax

    var promise = navigator.clipboard.readText()

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`DOMString`](../domstring) containing the textual contents of the clipboard. Returns an empty string if the clipboard is empty, does not contain text, or does not include a textual representation among the [`DataTransfer`](../datatransfer) objects representing the clipboard's contents.

To read non-text contents from the clipboard, use the [`read()`](read) method instead. You can write text to the clipboard using [`writeText()`](writetext).

## Example

This example retrieves the textual contents of the clipboard and inserts the returned text into an element's contents.

    navigator.clipboard.readText().then(
      clipText => document.getElementById("outbox").innerText = clipText);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboard-readtext">Clipboard API and events<br />
<span class="small">The definition of 'readText()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`readText`

66

79

63

Firefox only supports reading the clipboard in browser extensions, using the `"clipboardRead"` extension permission.

No

53

13.1

66

66

63

Firefox only supports reading the clipboard in browser extensions, using the `"clipboardRead"` extension permission.

47

13.4

9.0

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)
- [`Clipboard.writeText()`](writetext)
- [`Clipboard.write()`](write)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/readText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/readText</a>
