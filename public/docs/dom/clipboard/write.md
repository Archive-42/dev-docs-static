# Clipboard.write()

The [`Clipboard`](../clipboard) method `write()` writes arbitrary data, such as images, to the clipboard. This can be used to implement cut and copy functionality.

The `"clipboard-write"` permission of the [Permissions API](../permissions_api), is granted automatically to pages when they are in the active tab.

**Note:** Browser support for the asynchronous clipboard APIs is still in the process of being implemented. Be sure to check the [compatibility table](#browser%0A____compatibility) as well as [Clipboard availability](../clipboard#clipboard_availability) in [Clipboard](../clipboard) for more information.

## Syntax

    var promise = navigator.clipboard.write(data)

### Parameters

`data`  
An array of [`ClipboardItem`](../clipboarditem) objects containing data to be written to the clipboard.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved when the data has been written to the clipboard. The promise is rejected if the clipboard is unable to complete the clipboard access.

## Example

This example function replaces the current contents of the clipboard with a specified string.

    function setClipboard(text) {
      let data = [new ClipboardItem({ "text/plain": text })];

      navigator.clipboard.write(data).then(function() {
        /* success */
      }, function() {
        /* failure */
      });
    }

The code begins by creating a new [`ClipboardItem`](../clipboarditem) object into which the text will be placed for sending to the clipboard. The key of the object passed to the [`ClipboardItem`](../clipboarditem) constructor indicates the content type, the value indicates the content. The content could be a text or even a Blob (e.g. for copying images to the clipboard). Then `write()` is called, specifying both a fulfillment function and an error function.

### Example of copying canvas contents to the clipboard

    function copyCanvasContentsToClipboard(canvas, onDone, onError) {
      canvas.toBlob(function (blob) {
        let data = [new ClipboardItem({ [blob.type]: blob })];

        navigator.clipboard.write(data).then(function () {
          onDone();
        }, function (err) {
          onError(err);
        })
      });
    }

**Note**: You can only pass in one clipboard item at a time.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboard-write">Clipboard API and events<br />
<span class="small">The definition of 'write()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`write`

66

From version 76, the `image/png` MIME type is supported.

79

87

Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `"clipboardWrite"` permission can write to the clipboard at any time.

63

\["This method accepts a `DataTransfer` object instead of an array of `ClipboardItem` objects.", "Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `\"clipboardWrite\"` permission can write to the clipboard at any time."\]

No

63

13.1

66

From version 84, the `image/png` MIME type is supported.

66

From version 84, the `image/png` MIME type is supported.

87

Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `"clipboardWrite"` permission can write to the clipboard at any time.

63

\["This method accepts a `DataTransfer` object instead of an array of `ClipboardItem` objects.", "Writing to the clipboard is available without permission in secure contexts and browser extensions, but only from user-initiated event callbacks. Browser extensions with the `\"clipboardWrite\"` permission can write to the clipboard at any time."\]

54

13.4

12.0

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/write</a>
