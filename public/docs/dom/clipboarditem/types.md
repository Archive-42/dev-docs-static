# ClipboardItem.types

The read-only `types` property of the [`ClipboardItem`](../clipboarditem) interface returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [MIME types](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) available within the [`ClipboardItem`](../clipboarditem)

## Syntax

    var types = clipboardItem.types;

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of available [MIME types](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type).

## Examples

In the below example, we're returning all items on the clipboard via the [`clipboard.read()`](../clipboard/read) method. Then checking the `types` property for available types before utilizing the [`ClipboardItem.getType()`](gettype) method to return the [`Blob`](../blob) object. If no clipboards contents is found for the specified type, an error is returned.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboarditem-types">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardItem.types' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`types`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/types</a>
