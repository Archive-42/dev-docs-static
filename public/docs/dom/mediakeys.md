# MediaKeys

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaKeys` interface of [EncryptedMediaExtensions API](encrypted_media_extensions_api) represents a set of keys that an associated [`HTMLMediaElement`](htmlmediaelement) can use for decryption of media data during playback.

## Properties

None.

## Methods

[`MediaKeys.createSession()`](mediakeys/createsession)  
Returns a new [`MediaKeySession`](mediakeysession) object, which represents a context for message exchange with a content decryption module (CDM).

[`MediaKeys.setServerCertificate()`](mediakeys/setservercertificate)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a server certificate to be used to encrypt messages to the license server.

## Examples

    //TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#mediakeys-interface">Encrypted Media Extensions<br />
<span class="small">The definition of 'MediaKeys' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaKeys`

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

`createSession`

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

`setServerCertificate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeys</a>
