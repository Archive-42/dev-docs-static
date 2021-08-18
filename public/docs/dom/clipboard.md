# Clipboard

The `Clipboard` interface implements the [Clipboard API](clipboard_api), providing—if the user grants permission—both read and write access to the contents of the system clipboard. The Clipboard API can be used to implement cut, copy, and paste features within a web application.

The system clipboard is exposed through the global [`Navigator.clipboard`](navigator/clipboard) property.

Calls to the methods of the `Clipboard` object will not succeed if the user hasn't granted the needed permissions using the [Permissions API](permissions_api) and the `"clipboard-read"` or `"clipboard-write"` permission as appropriate.

**Note:** In reality, at this time browser requirements for access to the clipboard vary significantly. Please see the section [Clipboard availability](#clipboard_availability) for details.

All of the Clipboard API methods operate asynchronously; they return a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once the clipboard access has been completed. The promise is rejected if clipboard access is denied.

The **clipboard** is a data buffer that is used for short-term, data storage and/or data transfers, this can be between documents or applications  
It is usually implemented as an anonymous, temporary [data buffer](https://en.wikipedia.org/wiki/Data_buffer), sometimes called the paste buffer, that can be accessed from most or all programs within the environment via defined [programming interfaces](https://en.wikipedia.org/wiki/Application_programming_interface).

A typical application accesses clipboard functionality by mapping [user input](https://en.wikipedia.org/wiki/User_input) such as [keybindings](https://en.wikipedia.org/wiki/Keybinding), [menu selections](<https://en.wikipedia.org/wiki/Menu_(computing)>), etc. to these interfaces.

## Methods

_`Clipboard` is based on the [`EventTarget`](eventtarget) interface, and includes its methods._

[`read()`](clipboard/read)  
Requests arbitrary data (such as images) from the clipboard, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). When the data has been retrieved, the promise is resolved with a [`DataTransfer`](datatransfer) object that provides the data.

[`readText()`](clipboard/readtext)  
Requests text from the system clipboard; returns a `Promise` which is resolved with a [`DOMString`](domstring) containing the clipboard's text once it's available.

[`write()`](clipboard/write)  
Writes arbitrary data to the system clipboard. This asynchronous operation signals that it's finished by resolving the returned `Promise`.

[`writeText()`](clipboard/writetext)  
Writes text to the system clipboard, returning a `Promise` which is resolved once the text is fully copied into the clipboard.

## Clipboard availability

The asynchronous clipboard API is a relatively recent addition, and the process of implementing it in browsers is not yet complete. Due to both potential security concerns and technical complexities, the process of integrating this API is happening gradually in most browsers.

For example, Firefox does not yet support the `"clipboard-read"` and `"clipboard-write"` permissions, so access to the methods that access and change the contents of the clipboard are restricted in other ways.

For WebExtensions, you can request the clipboardRead and clipboardWrite permissions to be able to use clipboard.readText() and clipboard.writeText(). Content scripts applied on HTTP sites do not have access to the clipboard object. See [extensions in Firefox 63](https://blog.mozilla.org/addons/2018/08/31/extensions-in-firefox-63/).

In addition, [`read()`](clipboard/read) and [`write()`](clipboard/write) are disabled by default and require changing a preference to enable them. Check the compatibility tables for each method before using it.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-interface">Clipboard API and events<br />
<span class="small">The definition of 'Clipboard' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Clipboard`

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

## See also

- [`Document.execCommand()`](document/execcommand)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clipboard" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clipboard</a>
