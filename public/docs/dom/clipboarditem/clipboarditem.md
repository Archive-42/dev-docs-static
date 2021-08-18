# ClipboardItem()

The `ClipboardItem()` constructor of the [`Clipboard API`](../clipboard_api) creates a new [`ClipboardItem`](../clipboarditem) object which represents data to be stored or retrieved via the [`Clipboard API`](../clipboard_api), that is [`clipboard.write()`](../clipboard/write) and [`clipboard.read()`](../clipboard/read) respectively.

**Note**: Image format support varies by browser. See the browser compatibility table for the [`Clipboard`](../clipboard) interface.

## Syntax

    var ClipboardItem = new ClipboardItem(ClipboardItemData);

### Parameters

`ClipboardItemData`  
An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) as the key and data as the value. The data can represented as a [`Blob`](../blob), a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to either a blob or string.

`ClipboardItemOptions` <span class="badge inline optional">Optional</span>  
An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the following properties:

- `presentationStyle`: One of `"unspecified"`, `"inline"` or `"attachment"`. The default is `"unspecified"`.

**Note**: You can also work with text via the [`Clipboard.readText()`](../clipboard/readtext) and [`Clipboard.writeText()`](../clipboard/writetext) methods of the [`Clipboard`](../clipboard) interface.

## Examples

The below example requests a png image using the [`Fetch API`](../fetch_api), and in turn, the [`responses' blob()`](../body/blob) method, to create a new [`ClipboardItem`](../clipboarditem). This item is then written to the clipboard, using the [`Clipboard.write()`](../clipboard/write) method.

**Note**: You can only pass in one clipboard item at a time.

    async function writeClipImg() {
      try {
        const imgURL = '/myimage.png';
        const data = await fetch(imgURL);
        const blob = await data.blob();

        await navigator.clipboard.write([
          new ClipboardItem({
            [blob.type]: blob
          })
        ]);
        console.log('Fetched image copied.');
      } catch(err) {
        console.error(err.name, err.message);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboarditem">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardItem' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ClipboardItem`

66

The `ClipboardItem` constructor only accepts a blob as the item data, but not strings or Promises that resolve to strings or blobs. See [bug 1014310](https://crbug.com/1014310).

79

The `ClipboardItem` constructor only accepts a blob as the item data, but not strings or Promises that resolve to strings or blobs. See [bug 1014310](https://crbug.com/1014310).

87

No

Yes

The `ClipboardItem` constructor only accepts a blob as the item data, but not strings or Promises that resolve to strings or blobs. See [bug 1014310](https://crbug.com/1014310).

13.1

66

The `ClipboardItem` constructor only accepts a blob as the item data. Full implementation would also allow for a string or a Promise which resolves with either a string or blob. See [bug 1014310](https://crbug.com/1014310).

66

The `ClipboardItem` constructor only accepts a blob as the item data. Full implementation would also allow for a string or a Promise which resolves with either a string or blob. See [bug 1014310](https://crbug.com/1014310).

87

Yes

The `ClipboardItem` constructor only accepts a blob as the item data, but not strings or Promises that resolve to strings or blobs. See [bug 1014310](https://crbug.com/1014310).

13.4

9.0

The `ClipboardItem` constructor only accepts a blob as the item data, but not strings or Promises that resolve to strings or blobs. See [bug 1014310](https://crbug.com/1014310).

## See also

- [Clipboard API](../clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/ClipboardItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem/ClipboardItem</a>
