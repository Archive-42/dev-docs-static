# MediaKeySession.expiration

The `MediaKeySession.expiration` read-only property returns the time after which the keys in the current session can no longer be used to decrypt media data, or NaN if no such time exists. This value is determined by the CDM and measured in milliseconds since January 1, 1970, UTC. This value may change during a session lifetime, such as when an action triggers the start of a window.

## Syntax

    var expirationTime = mediaKeySessionObj.expiration;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#dom-mediakeysession-expiration">Encrypted Media Extensions<br />
<span class="small">The definition of 'expiration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`expiration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/expiration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/expiration</a>
