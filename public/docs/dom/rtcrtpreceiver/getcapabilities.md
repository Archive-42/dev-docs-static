RTCRtpReceiver.getCapabilities() static function
================================================

The *static function* `RTCRtpReceiver.getCapabilities()` returns an [`RTCRtpCapabilities`](../rtcrtpcapabilities) object describing the codecs and capabilities supported by [`RTCRtpReceiver`](../rtcrtpreceiver)s on the current device.

You can, similarly, obtain the capabilities of [`RTCRtpSender`](../rtcrtpsender)s by calling the static function [`RTCRtpSender.getCapabilities()`](../rtcrtpsender/getcapabilities).

Syntax
------

    let rtpCapabilities = RTCRtpReceiver.getCapabilities(kind);

### Parameters

`kind`  
A [`DOMString`](../domstring) indicating the type of media for which you wish to get the device's capability to receive. All browsers support the primary media kinds: `audio` and `video`.

### Return value

An [`RTCRtpCapabilities`](../rtcrtpcapabilities) object stating what capabilities the browser has for receiving the specified media kind over an [`RTCPeerConnection`](../rtcpeerconnection). If the browser doesn't have any support for the given media kind, the returned value is `null`.

Description
-----------

As a static function, this is always called using the form:

    capabilities = RTCRtpReceiver.getCapabilities("audio");

The returned set of capabilities is the most optimistic possible list. It is entirely possible that certain combinations of options may fail to work when you actually try to use them.

Calling `RTCRtpReceiver.getCapabilities()` doesn't prime the browser in any way to handle media. Nothing is loaded, fetched, or otherwise prepared. It's a means of determining what might be usable before starting to try to access media.

Because the set of capabilities available tend to be stable for a length of time (people don't install and uninstall codecs and the like very often), the media capabilities can in whole or in part provide a cross-origin method for identifying a user. For that reason, in privacy-sensitive contexts, the browser may choose to obscure the capabilities; this might be done, for example, by leaving out rarely-used codec configurations.

Example
-------

The function below returns a Boolean indicating whether or not the device supports receiving H.264 video on a WebRTC connection.

Since `RTCRtpReceiver.getCapabilities()` actually only indicates *probable* support, attempting to receive H.264 video might still fail even after getting a positive response from this function.

    function canReceiveH264() {
      let capabilities = RTCRtpReceiver.getCapabilities("video");

      capabilities.codecs.forEach((codec) => {
        if (codec.mimeType === "video/H264") {
          return true;
        }
      });
      return false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiver-getcapabilities">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiver.getCapabilities()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

59

12

Yes

No

46

12.1

59

59

Yes

43

12.2

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getCapabilities</a>
