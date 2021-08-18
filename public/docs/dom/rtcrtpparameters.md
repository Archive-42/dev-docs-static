RTCRtpParameters
================

The `RTCRtpParameters` dictionary is the basic object describing the parameters of an [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) transport. It is extended separately for senders and receivers in the form of the [`RTCRtpSendParameters`](rtcrtpsendparameters) and [`RTCRtpReceiveParameters`](rtcrtpreceiveparameters) dictionaries.

To obtain the parameters of a sender or receiver, call its `getParameters()` method:

-   [`getParameters()`](rtcrtpsender/getparameters)
-   [`getParameters()`](rtcrtpreceiver/getparameters)

Properties
----------

<span class="page-not-created">`codecs`</span>  
An array of [`RTCRtpCodecParameters`](rtcrtpcodecparameters) objects describing the set of codecs from which the sender or receiver will choose. This parameter cannot be changed once initially set.

<span class="page-not-created">`headerExtensions`</span>  
An array of zero or more RTP header extensions, each identifying an extension supported by the sender or receiver. Header extensions are described in [RFC 3550: 5.3.1](https://tools.ietf.org/html/rfc3550). This parameter cannot be changed once initially set.

<span class="page-not-created">`rtcp`</span>  
An [`RTCRtcpParameters`](rtcrtcpparameters) object providing the configuration parameters used for [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) on the sender or receiver. This parameter cannot be changed once initially set.

Examples
--------

This example obtains the canonical name (CNAME) being used for [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) on an [`RTCRtpSender`](rtcrtpsender) or [`RTCRtpReceiver`](rtcrtpreceiver).

    function getRtpCNAME(rtpObject) {
      let parameters = rtpObject.getParameters();

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpParameters</a>
