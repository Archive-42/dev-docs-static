RTCRtpReceiveParameters
=======================

The `RTCRtpReceiveParameters` dictionary, based upon the [`RTCRtpParameters`](rtcrtpparameters) dictionary, is returned by the [`RTCRtpReceiver`](rtcrtpreceiver) method [`getParameters()`](rtcrtpreceiver/getparameters). It describes the parameters being used by the receiver's [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) connection to the remote peer.

Properties
----------

*This dictionary currently has no properties of its own; it exists for future expansion. It inherits all of the properties of its parent, [`RTCRtpParameters`](rtcrtpparameters).*

Examples
--------

This example obtains the canonical name (CNAME) being used for [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) on an [`RTCRtpReceiver`](rtcrtpreceiver).

    function getRtcpCNAME(receiver) {
      let parameters = receiver.getParameters();

      return parameters.rtcp.cname;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiveparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiveParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCRtpReceiveParameters`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`RTCRtpSendParameters`](rtcrtpsendparameters) and [`RTCRtpSender.setParameters()`](rtcrtpsender/setparameters)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiveParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiveParameters</a>
