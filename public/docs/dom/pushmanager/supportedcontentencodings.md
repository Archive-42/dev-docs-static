PushManager.supportedContentEncodings
=====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `supportedContentEncodings` read-only property of the [`PushManager`](../pushmanager) interface returns an array of supported content codings that can be used to encrypt the payload of a push message.

Syntax
------

    var encodings[] = PushManager.supportedContentEncodings

### Value

An array of strings.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushmanager-supportedcontentencodings">Push API<br />
<span class="small">The definition of 'supportedContentEncodings' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`supportedContentEncodings`

60

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

47

No

No

60

48

Push enabled by default.

44

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/supportedContentEncodings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/supportedContentEncodings</a>
