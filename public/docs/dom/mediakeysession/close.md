# MediaKeySession.close()

The `MediaKeySession.close()` method notifies that the current media session is no longer needed, and that the content decryption module should release any resources associated with this object and close it. Then, it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Syntax

    mediaKeySession.close().then(function() { ... });

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#dom-mediakeysession-close">Encrypted Media Extensions<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`close`

42

13

38

No

Yes

12.1

43

42

38

Yes

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/close</a>
