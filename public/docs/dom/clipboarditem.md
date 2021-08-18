# ClipboardItem

The `ClipboardItem` interface of the [`Clipboard API`](clipboard_api) represents a single item format, used when reading or writing data via the [`Clipboard API`](clipboard_api). That is [`clipboard.read()`](clipboard/read) and [`clipboard.write()`](clipboard/write) respectively.

The benefit of having the `ClipboardItem` interface to represent data, is that it enables developers to cope with the varying scope of file types and data easily.

Access to the contents of the clipboard is gated behind the [Permissions API](permissions_api): The `clipboard-write` permission is granted automatically to pages when they are in the active tab. The `clipboard-read` permission must be requested, which you can do by trying to read data from the clipboard.

**Note**: To work with text see the [`Clipboard.readText()`](clipboard/readtext) and [`Clipboard.writeText()`](clipboard/writetext) methods of the [`Clipboard`](clipboard) interface.

**Note**: You can only pass in one clipboard item at a time.

## Constructor

[`ClipboardItem.ClipboardItem()`](clipboarditem/clipboarditem)  
Creates a new `ClipboardItem` object, with the [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) as the key and [`Blob`](blob) as the value

## Properties

_This interface provides the following properties._

[`types`](clipboarditem/types) <span class="badge inline readonly">Read only </span>  
Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of MIME types available within the `ClipboardItem`.

[`presentationStyle`](clipboarditem/presentationstyle) <span class="badge inline readonly">Read only </span>  
Returns one of the following: `"unspecified"`, `"inline"` or `"attachment"`.

## Methods

_This interface defines the following methods._

[`getType()`](clipboarditem/gettype)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](blob) of the requested [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type), or an error if the MIME type is not found.

## Examples

### Writing To Clipboard

Here we're writing a new [`ClipboardItem.ClipboardItem()`](clipboarditem/clipboarditem) to the [`clipboard`](clipboard_api) by requesting a png image using the [`Fetch API`](fetch_api), and in turn, the [`responses' blob()`](body/blob) method, to create the new [`ClipboardItem`](clipboarditem).

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

### Reading From The Clipboard

Here we're returning all items on the clipboard via the [`clipboard.read()`](clipboard/read) method. Then utilizing the [`ClipboardItem.types`](clipboarditem/types) property to set the [`getType()`](clipboarditem/gettype) argument and return the corresponding blob object.

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

`presentationStyle`

No

No

87

No

No

13.1

No

No

87

No

13.4

No

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

- [Clipboard API](clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem</a>
