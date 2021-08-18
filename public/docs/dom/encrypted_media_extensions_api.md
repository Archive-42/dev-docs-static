# Encrypted Media Extensions API

The Encrypted Media Extensions API provides interfaces for controlling the playback of content which is subject to a digital restrictions management scheme.

## Interfaces

[`MediaKeyMessageEvent`](mediakeymessageevent)  
Contains the content and related data when the content decryption module (CDM) generates a message for the session.

[`MediaKeys`](mediakeys)  
Represents a set of keys that an associated [`HTMLMediaElement`](htmlmediaelement) can use for decryption of media data during playback.

[`MediaKeySession`](mediakeysession)  
Represents a context for message exchange with a content decryption module (CDM).

[`MediaKeyStatusMap`](mediakeystatusmap)  
Is a read-only map of media key statuses by key IDs.

[`MediaKeySystemAccess`](mediakeysystemaccess)  
Provides access to a Key System for decryption and/or a content protection provider.

[`MediaKeySystemConfiguration`](mediakeysystemconfiguration)  
Provides configuration information about the media key system.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/">Encrypted Media Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Encrypted_Media_Extensions_API`

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

13

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

No

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.1

43

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until version 58."\]

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.4

4.0

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Samsung Internet 7.0."\]

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API</a>
