# ClipboardItem.presentationStyle

The read-only `presentationStyle` property of the [`ClipboardItem`](../clipboarditem) interface returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) indicating how an item should be presented.

## Syntax

    var presentationStyle = clipboardItem.presentationStyle;

### Value

One of either `"unspecified"`, `"inline"` or `"attachment"`.

## Examples

In the below example, we're returning all items on the clipboard via the [`clipboard.read()`](../clipboard/read) method, then logging the `presentationStyle` property.

    async function getClipboardContents() {
      try {
        const clipboardItems = await navigator.clipboard.read();

        for (const clipboardItem of clipboardItems) {

          console.log(clipboardItem.presentationStyle);

        }

      } catch (err) {
        console.error(err.name, err.message);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboarditem-presentationstyle">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardItem.presentationStyle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`presentationStyle`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/presentationStyle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/presentationStyle</a>
