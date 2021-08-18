RTCRtcpParameters
=================

The `RTCRtcpParameters` dictionary provides parameters of an [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) connection. It's used as the value of the <span class="page-not-created">`rtcp`</span> property of the [parameters](rtcrtpparameters) of an [`RTCRtpSender`](rtcrtpsender) or [`RTCRtpReceiver`](rtcrtpreceiver).

Properties
----------

<span class="page-not-created">`cname`</span>  
The Canonical Name (CNAME) being used by RTCP. This is used, for example, in SDES (SDP security descriptions) messages, described in [RFC 4568](https://tools.ietf.org/html/rfc4568). This property cannot be changed once initialized.

<span class="page-not-created">`reducedSize`</span>  
A Boolean value indicating whether or not reduced size RTCP is configured. If this value is `true`, reduced size RTCP (described in [RFC 5506](https://tools.ietf.org/html/rfc5506)) is in effect. If `false`, compund RTCP is in use, as found in [RFC 3550](https://tools.ietf.org/html/rfc3550). This property cannot be changed once initialized.

Examples
--------

This example obtains the canonical name (CNAME) being used for RTCP on an [`RTCRtpSender`](rtcrtpsender) or [`RTCRtpReceiver`](rtcrtpreceiver).

    function getRtpCNAME(rtpObject) {
      let parameters = rtpObject.getParameters();

      return parameters.rtcp.cname;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtcpparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtcpParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCRtcpParameters`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtcpParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtcpParameters</a>
