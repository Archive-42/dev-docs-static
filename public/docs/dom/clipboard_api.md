# Clipboard API

The **Clipboard API** provides the ability to respond to clipboard commands (cut, copy, and paste) as well as to asynchronously read from and write to the system clipboard. Access to the contents of the clipboard is gated behind the [Permissions API](permissions_api): The `clipboard-write` permission is granted automatically to pages when they are in the active tab. The `clipboard-read` permission must be requested, which you can do by trying to read data from the clipboard.

**Note:** This API is _not available_ in [Web Workers](web_workers_api) (not exposed via [`WorkerNavigator`](workernavigator)).

This API is designed to supersede accessing the clipboard using [`document.execCommand()`](document/execcommand).

## Accessing the clipboard

Instead of creating a `Clipboard` object through instantiation, you access the system clipboard through the [`Navigator.clipboard`](navigator/clipboard) global:

    navigator.clipboard.readText().then(
      clipText => document.querySelector(".editor").innerText += clipText);

This snippet fetches the text from the clipboard and appends it to the first element found with the class `editor`. Since [`readText()`](clipboard/readtext) (and [`read()`](clipboard/read), for that matter) returns an empty string if the clipboard isn't text, this code is safe.

## Interfaces

[`Clipboard`](clipboard) <span class="notecard inline secure">Secure context</span>  
Provides an interface for reading and writing text and data to or from the system clipboard. The specification refers to this as the 'Async Clipboard API.'

[`ClipboardEvent`](clipboardevent) <span class="notecard inline secure">Secure context</span>  
Represents events providing information related to modification of the clipboard, that is [`cut`](element/cut_event), [`copy`](element/copy_event), and [`paste`](element/paste_event) events. The specification refers to this as the 'Clipboard Event API'.

[`ClipboardItem`](clipboarditem) <span class="notecard inline secure">Secure context</span>  
Represents a single item format, used when reading or writing data.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/">Clipboard API and events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Clipboard_API`

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

`Clipboard_API`

Yes

12

22

4

Yes

Yes

Yes

Yes

22

Yes

Yes

Yes

`ClipboardEvent`

58

≤79

22

No

45

Yes

58

58

22

43

Yes

7.0

`clipboardData`

Yes

12

22

5

Yes

Yes

Yes

Yes

22

Yes

Yes

Yes

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

`Clipboard_API`

66

79

63

No

53

13.1

66

66

63

47

13.4

9.0

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

BCD tables only load in the browser

### ClipboardEvent

BCD tables only load in the browser

### ClipboardItem

BCD tables only load in the browser

## See also

- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)
- [Permissions API](permissions_api)
- [Using the Permissions API](permissions_api/using_the_permissions_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API</a>
