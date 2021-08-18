RTCRtpSender.getParameters()
============================

The `getParameters()` method of the [`RTCRtpSender`](../rtcrtpsender) interface returns an [`RTCRtpSendParameters`](../rtcrtpsendparameters) object describing the current configuration for the encoding and transmission of media on the sender's [`track`](track).

Syntax
------

    var rtpSendParameters = rtpSender.getParameters()

### Parameters

None.

### Return value

An [`RTCRtpSendParameters`](../rtcrtpsendparameters) object indicating the current configuration of the sender.

Examples
--------

This example gets the sender's current transaction ID; the transaction ID uniquely identifies the current set of parameters, to ensure that calls to [`setParameters()`](setparameters) are always handled in the correct order, avoiding inadvertently overwriting parameters with older parameters.

    function getSenderTransactionID(sender) {
      let parameters = sender.getParameters();

      return parameters.transactionId;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-getparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'getParameters()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

68

≤79

Yes

No

55

11

68

68

Yes

48

11

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getParameters</a>
