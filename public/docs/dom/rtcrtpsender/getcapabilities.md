RTCRtpSender.getCapabilities() static function
==============================================

The *static function* `RTCRtpSender.getCapabilities()` returns an [`RTCRtpCapabilities`](../rtcrtpcapabilities) object describing the codecs and capabilities supported by the [`RTCRtpSender`](../rtcrtpsender).

You can, similarly, obtain the capabilities of [`RTCRtpReceiver`](../rtcrtpreceiver)s by calling the static function [`RTCRtpReceiver.getCapabilities()`](../rtcrtpreceiver/getcapabilities).

Syntax
------

    let rtpCapabilities = RTCRtpSender.getCapabilities(kind);

### Parameters

`kind`  
A [`DOMString`](../domstring) indicating the type of media for which you wish to get the sender's capability to receive. All browsers support the primary media kinds: `audio` and `video`.

### Return value

An [`RTCRtpCapabilities`](../rtcrtpcapabilities) object stating what capabilities the browser has for sending the specified media kind over an [`RTCPeerConnection`](../rtcpeerconnection). If the browser doesn't have any support for the given media kind, the returned value is `null`.

Description
-----------

As a static function, this is always called using the form:

    capabilities = RTCRtpSender.getCapabilities("audio");

The returned set of capabilities is the most optimistic possible list. It is entirely possible that certain combinations of options may fail to work when you actually try to use them.

Calling `RTCRtpSender.getCapabilities()` doesn't prime the browser in any way to handle media. Nothing is loaded, fetched, or otherwise prepared. It's a means of determining what might be usable before starting to try to access media.

Because the set of capabilities available tend to be stable for a length of time (people don't install and uninstall codecs and the like very often), the media capabilities can in whole or in part provide a cross-origin method for identifying a user. For that reason, in privacy-sensitive contexts, the browser may choose to obscure the capabilities; this might be done, for example, by leaving out rarely-used codec configurations.

Example
-------

The function below returns a Boolean indicating whether or not the device supports sending H.264 video on an [`RTCRtpSender`](../rtcrtpsender).

Since `RTCRtpSender.getCapabilities()` actually only indicates *probable* support, H.264 support might still fail even after getting a positive response from this function.

    function canSendH264() {
      let capabilities = RTCRtpSender.getCapabilities("video");

      capabilities.codecs.forEach((codec) => {
        if (codec.mimeType === "video/H264") {
          return true;
        }
      });
      return false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-getcapabilities">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.getCapabilities()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`getCapabilities`

69

12

?

No

56

12.1

69

69

?

48

12.2

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getCapabilities</a>
