# MediaKeyMessageEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaKeyMessageEvent` interface of the [EncryptedMediaExtensions API](encrypted_media_extensions_api) contains the content and related data when the content decryption module generates a message for the session.

## Constructor

[`MediaKeyMessageEvent()`](mediakeymessageevent/mediakeymessageevent)  
Creates a new instance of `MediaKeyMessageEvent`.

## Properties

Inherits properties from its parent, [`Event`](event).

[`MediaKeyMessageEvent.message`](mediakeymessageevent/message) <span class="badge inline readonly">Read only </span>  
Returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) with a message from the content decryption module. Messages vary by key system.

[`MediaKeyMessageEvent.messageType`](mediakeymessageevent/messagetype) <span class="badge inline readonly">Read only </span>  
Indicates the type of message. May be one of `license-request`, `license-renewal`, `license-release`, or `individualization-request`.

## Methods

Inherits methods from its parent, [`Event`](event).

## Examples

    // TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#mediakeymessageevent">Encrypted Media Extensions<br />
<span class="small">The definition of 'MediaKeyMessageEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaKeyMessageEvent`

42

13

Yes

No

Yes

Yes

No

42

Yes

Yes

Yes

4.0

`MediaKeyMessageEvent`

42

13

?

No

?

Yes

No

42

?

?

Yes

4.0

`message`

42

13

Yes

No

Yes

Yes

No

42

Yes

Yes

Yes

4.0

`messageType`

42

13

Yes

No

Yes

Yes

No

42

Yes

Yes

Yes

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyMessageEvent</a>
