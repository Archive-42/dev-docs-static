RTCRtpTransceiver.setCodecPreferences()
=======================================

The [`RTCRtpTransceiver`](../rtcrtptransceiver) method `setCodecPreferences()` configures the transceiver's codecs given a list of [`RTCRtpCodecCapability`](../rtcrtpcodeccapability) objects specifying the new preferences for each [codec](https://developer.mozilla.org/en-US/docs/Glossary/Codec). The specified set of codecs and configurations will be used for all future connections including this transceiver until this method is called again.

When preparing to open an [`RTCPeerConnection`](../rtcpeerconnection), you can change the codec parameters from the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) default configuration by calling `setCodecParameters()` *before* calling either [`RTCPeerConnection.createOffer()`](../rtcpeerconnection/createoffer) or [`createAnswer()`](../rtcpeerconnection/createanswer).

A guide to codecs supported by WebRTC—and each codec's positive and negative characteristics—can be found in [Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs).

Syntax
------

    rtcRtpTransceiver.setCodecPreferences(codecs)

### Parameters

`codecs`  
An array of [`RTCRtpCodecCapability`](../rtcrtpcodeccapability) objects, in order of preference, each providing the parameters for one of the transceiver's supported codecs. If `codecs` is empty, the codec configurations are all returned to the user agent's defaults.

**Note:** Any codecs not included in `codecs` will not be considered during the process of negotiating a connection. This lets you prevent the use of codecs you don't wish to use.

### Return value

`undefined`

### Exceptions

`InvalidAccessError`  
The `codecs` list includes one or more codecs which are not supported by the transceiver.

Usage notes
-----------

### Getting a list of supported codecs

You can only include in the `codecs` list codecs which the transceiver actually supports. That means that either the associated [`RTCRtpSender`](../rtcrtpsender) or the [`RTCRtpReceiver`](../rtcrtpreceiver) needs to support every codec in the list. If any unsupported codecs are listed, the browser will throw an `InvalidAccessError` exception when you call this method.

A good approach to setting codec preferences is to first get the list of codecs that are actually supported, then modify that list to match what you want. Pass the altered list into `setCodecPreferences()` to specify your preferences.

To determine which codecs are supported by the transceiver, call the sender's [`getCapabilities()`](../rtcrtpsender/getcapabilities) and the receiver's [`getCapabilities()`](../rtcrtpreceiver/getcapabilities) methods and get the <span class="page-not-created">`codecs`</span> list from the results of each.

The following code snippet demonstrates how to get both the list of codecs supported by the transceiver's [`RTCRtpSender`](../rtcrtpsender) and [`RTCRtpReceiver`](../rtcrtpreceiver).

    var availSendCodecs = transceiver.sender.getCapabilities("video").codecs;
    var availReceiveCodecs = transceiver.receiver.getCapabilities("video").codecs;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiver-setcodecpreferences">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.setCodecPreferences()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`setCodecPreferences`

No

No

No

No

No

13.1

No

No

No

No

13.4

No

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs)
-   [Introduction to the Real-time Transport Protocol (RTP)](../webrtc_api/intro_to_rtp)
-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/setCodecPreferences" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/setCodecPreferences</a>
