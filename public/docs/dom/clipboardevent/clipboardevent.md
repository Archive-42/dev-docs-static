# ClipboardEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ClipboardEvent()` constructor returns a newly created [`ClipboardEvent`](../clipboardevent), representing an event providing information related to modification of the clipboard, that is `cut`, `copy`, and `paste` events.

## Syntax

    var clipboardEvent = new ClipboardEvent(type[, options]);

### Parameters

_The `ClipboardEvent()` constructor also inherits arguments from [`Event()`](../event/event)._

_type_  
Is a [`DOMString`](../domstring) representing the name of the type of the `ClipboardEvent`. It is case-sensitive and can be: `'copy'`, `'cut'`, or `'paste'`.

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `clipboardData`: A [`DataTransfer`](../datatransfer) containing the data concerned by the clipboard event.
- `dataType`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>: A [`DOMString`](../domstring) containing the MIME-type of the data contained in the `data` argument.
- `data`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>: A [`DOMString`](../domstring) containing the data concerned by the clipboard event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#dom-clipboardevent-clipboardevent">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- Copy-related events: `copy`, `cut`, `paste`
- The [`ClipboardEvent`](../clipboardevent) interface it belongs to.
- [Clipboard API](../clipboard_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent/ClipboardEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent/ClipboardEvent</a>
