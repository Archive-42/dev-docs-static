# Clipboard.read()

The `read()` method of the [`Clipboard`](../clipboard) interface requests a copy of the clipboard's contents, delivering the data to the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) when the promise is resolved. Unlike [`readText()`](readtext), the `read()` method can return arbitrary data, such as images. This method can also return text.

To read from the clipboard, you must first have the `"clipboard-read"` permission.

**Note:** The asynchronous Clipboard and [Permissions APIs](../permissions_api) are still in the process of being integrated into most browsers, so they often deviate from the official rules for permissions and the like. Be sure to review the [compatibility table](#browser%0A____compatibility) before using these methods.

## Syntax

    var promise = navigator.clipboard.read();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`DataTransfer`](../datatransfer) object containing the clipboard's contents. The promise is rejected if permission to access the clipboard is not granted.

## Example

After using [`navigator.permissions.query()`](../permissions/query) to find out if we have (or if the user will be prompted to allow) `"clipboard-read"` access, this example fetches the data currently on the clipboard. If it's not a png image, an error message is presented. Otherwise, an image element referred to using the variable `imgElem` has its source replaced with the clipboard's contents.

    // First, ask the Permissions API if we have some kind of access to
    // the "clipboard-read" feature.

    navigator.permissions.query({name: "clipboard-read"}).then(result => {
      // If permission to read the clipboard is granted or if the user will
      // be prompted to allow it, we proceed.

      if (result.state == "granted" || result.state == "prompt") {
        navigator.clipboard.read().then(data => {
          for (let i=0; i<data.items.length; i++) {
            if (data.items[i].type != "image/png") {
              alert("Clipboard contains non-image data. Unable to access it.");
            } else {
              const blob = data.items[i].getType("image/png");
              imgElem.src = URL.createObjectURL(blob);
            }
          }
        });
      }
    });

**Note:** At this time, while Firefox does implement `read()`, it does not recognize the `"clipboard-read"` permission, so attempting to use the [Permissions API](../permissions_api) to manage access to the API will not work.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboard-read">Clipboard API and events<br />
<span class="small">The definition of 'read()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`read`

86

From version 86, the `text/html` MIME type is supported.

76

From version 76, the `image/png` MIME type is supported.

66

Images are not supported.

79

87

Firefox only supports reading the clipboard in browser extensions, using the `"clipboardRead"` extension permission.

63-87

\["This method returns a `DataTransfer` object instead of an array of `ClipboardItem` objects.", "Firefox only supports reading the clipboard in browser extensions, using the `\"clipboardRead\"` extension permission."\]

No

63

13.1

84

From version 84, the `image/png` MIME type is supported.

66

Images are not supported.

86

From version 86, the `text/html` MIME type is supported.

84

From version 84, the `image/png` MIME type is supported.

66

Images are not supported.

87

Firefox only supports reading the clipboard in browser extensions, using the `"clipboardRead"` extension permission.

63-87

\["This method returns a `DataTransfer` object instead of an array of `ClipboardItem` objects.", "Firefox only supports reading the clipboard in browser extensions, using the `\"clipboardRead\"` extension permission."\]

54

13.4

12.0

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/read" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/read</a>
