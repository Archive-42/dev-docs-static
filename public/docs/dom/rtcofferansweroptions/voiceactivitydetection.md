RTCOfferAnswerOptions.voiceActivityDetection
============================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `voiceActivityDetection` property of the **[`RTCOfferAnswerOptions`](../rtcofferansweroptions)** dictionary is used to specify whether or not to use automatic voice detection for the audio on an [`RTCPeerConnection`](../rtcpeerconnection). The default value, `true`, indicates that voice detection should be used and that if possible, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) should automatically disable or mute outgoing audio when the audio source is not sensing a human voice.

Syntax
------

    var options = {
      voiceActivityDetection: trueOrFalse
    };

### Value

A Boolean value indicating whether or not the connection should use voice detection once running. The default value, `true`, indicates that the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) should monitor the audio coming from the microphone or other audio source and automatically cease transmitting data or mute when the user isn't speaking into the microphone,

A value of `false` indicates that the audio should continue to be transmitted regardless of whether or not speech is detected.

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

`voiceActivityDetection`

50

≤79

No

No

?

?

50

50

No

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferAnswerOptions/voiceActivityDetection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferAnswerOptions/voiceActivityDetection</a>
