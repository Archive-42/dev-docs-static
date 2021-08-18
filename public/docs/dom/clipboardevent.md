# ClipboardEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ClipboardEvent` interface represents events providing information related to modification of the clipboard, that is `cut`, `copy`, and `paste` events.

## Constructor

[`ClipboardEvent()`](clipboardevent/clipboardevent)  
Creates a `ClipboardEvent` event with the given parameters.

## Properties

_Also inherits properties from its parent [`Event`](event)_.

[`ClipboardEvent.clipboardData`](clipboardevent/clipboarddata) <span class="badge inline readonly">Read only </span>  
Is a [`DataTransfer`](datatransfer) object containing the data affected by the user-initiated `cut`, `copy`, or `paste` operation, along with its MIME type.

## Methods

_No specific methods; inherits methods from its parent [`Event`](event)_.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/clipboard-apis/#clipboard-event-interfaces">Clipboard API and events<br />
<span class="small">The definition of 'ClipboardEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- Copy-related events: `copy`, `cut`, `paste`
- [Clipboard API](clipboard_api)
- [Async Clipboard API demo on Glitch](https://async-clipboard-api.glitch.me/)
- [Image support for Async Clipboard article](https://web.dev/image-support-for-async-clipboard/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ClipboardEvent</a>
