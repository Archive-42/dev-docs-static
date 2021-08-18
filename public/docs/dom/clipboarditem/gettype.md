# ClipboardItem.getType()

The `getType()` method of the [`ClipboardItem`](../clipboarditem) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](../blob) of the requested [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) or an error if the MIME type is not found.

## Syntax

    var blob = clipboardItem.getType(type);

### Parameters

`type`  
A valid [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](../blob) object.

### Exceptions

`DOMException`  
The `type` does not match a known [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type).

`TypeError`  
No parameter is specified or the `type` is not that of the [`ClipboardItem`](../clipboarditem).

## Examples

In the following example, we're returning all items on the clipboard via the [`clipboard.read()`](../clipboard/read) method. Then utilizing the [`ClipboardItem.types`](types) property to set the `getType()` argument and return the corresponding blob object.

    async function getClipboardContents() {
      try {
        const clipboardItems = await navigator.clipboard.read();

        for (const clipboardItem of clipboardItems) {

          for (const type of clipboardItem.types) {
            const blob = await clipboardItem.getType(type);
            // we can now use blob here
          }

        }

      } catch (err) {
        console.error(err.name, err.message);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboarditem-gettype-type-type">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardItem.getType()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getType`

66

79

87

No

Yes

13.1

66

66

87

Yes

13.4

9.0

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/getType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/getType</a>
