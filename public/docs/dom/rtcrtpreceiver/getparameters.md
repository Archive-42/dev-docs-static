RTCRtpReceiver.getParameters()
==============================

The `getParameters()` method of the [`RTCRtpReceiver`](../rtcrtpreceiver) interface returns an [`RTCRtpReceiveParameters`](../rtcrtpreceiveparameters) object describing the current configuration for the encoding and transmission of media on the receiver's [`track`](track).

Syntax
------

    let rtpReceiveParameters = rtpReceiver.getParameters();

### Parameters

None.

### Return value

An [`RTCRtpReceiveParameters`](../rtcrtpreceiveparameters) object indicating the current configuration of the receiver.

Examples
--------

This example obtains the canonical name (CNAME) being used for [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) on an [`RTCRtpReceiver`](../rtcrtpreceiver).

    function getRtcpCNAME(receiver) {
      let parameters = receiver.getParameters();

      return parameters.rtcp.cname;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiver-getparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiver.getParameters()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getParameters`

59

≤79

Yes

No

46

11

59

59

Yes

43

11

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getParameters</a>
