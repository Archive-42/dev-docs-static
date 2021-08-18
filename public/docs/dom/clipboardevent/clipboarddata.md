# ClipboardEvent.clipboardData

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ClipboardEvent.clipboardData` property holds a [`DataTransfer`](../datatransfer) object, which can be used:

- to specify what data should be put into the clipboard from the `cut` and `copy` event handlers, typically with a [`setData(format, data)`](../datatransfer/setdata) call;
- to obtain the data to be pasted from the `paste` event handler, typically with a [`getData(format)`](../datatransfer/getdata) call.

See the `cut`, `copy`, and `paste` events documentation for more information.

## Syntax

    data = ClipboardEvent.clipboardData

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboardevent-clipboarddata">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardEvent.clipboardData' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- Copy-related events: `copy`, `cut`, `paste`
- The [`ClipboardEvent`](../clipboardevent) interface it belongs to.
- [Clipboard API](../clipboard_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent/clipboardData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent/clipboardData</a>
