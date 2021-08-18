Navigator.clipboard
===================

The [Clipboard API](../clipboard_api) adds to the **[`Navigator`](../navigator)** interface the read-only `clipboard` property, which returns the [`Clipboard`](../clipboard) object used to read and write the clipboard's contents. The Clipboard API can be used to implement cut, copy, and paste features within a web application.

Use of the asynchronous clipboard read and write methods requires that the user grant the web site or app permission to access the clipboard. This permission must be obtained from the [Permissions API](../permissions_api) using the `"clipboard-read"` and/or `"clipboard-write"` permissions.

Syntax
------

    theClipboard = navigator.clipboard;

### Value

The [`Clipboard`](../clipboard) object used to access the system clipboard.

Examples
--------

The following code uses `navigator.clipboard` to access the system clipboard in order to read the contents of the clipboard.

    navigator.clipboard.readText().then(
      clipText => document.querySelector(".cliptext").innerText = clipText);

This snippet replaces the contents of the element whose class is `"cliptext"` with the text contents of the clipboard. Perhaps this code is being used in a browser extension that displays the current clipboard contents, automatically updating periodically or when specific events fire.

If the clipboard is empty or doesn't contain text, the `"cliptext"` element's contents are cleared. This happens because [`readText()`](../clipboard/readtext) returns an empty string if the clipboard is empty or doesn't contain text.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#navigator-clipboard">Clipboard API and events<br />
<span class="small">The definition of 'navigator.clipboard' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`clipboard`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clipboard" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clipboard</a>
