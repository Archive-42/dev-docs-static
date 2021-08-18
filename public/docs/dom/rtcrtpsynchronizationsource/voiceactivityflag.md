RTCRtpSynchronizationSource.voiceActivityFlag
=============================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only `voiceActivityFlag` property of the [`RTCRtpSynchronizationSource`](../rtcrtpsynchronizationsource) interface indicates whether or not the most recent RTP packet on the source includes voice activity. This is only present if the stream is using the voice activity detection feature; see the `RTCOfferOptions` flag `voiceActivityDetection`.

Syntax
------

    var voiceActivity = RTCRtpSynchronizationSource.voiceActivityFlag

### Value

A Boolean value which is `true` if voice activity is present in the most recently received RTP packet played by the associated source, or `false` if voice activity is not present.

This property is omitted entirely if voice activity detection is not enabled on the source, or if the [RFC 6464](https://tools.ietf.org/html/rfc6464) extension header isn't present.

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

`voiceActivityFlag`

No

No

59

No

No

?

No

No

59

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSynchronizationSource/voiceActivityFlag" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSynchronizationSource/voiceActivityFlag</a>
