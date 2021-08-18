RTCRtpCodecParameters
=====================

The [`RTCRtpCodecParameters`](rtcrtpcodecparameters) dictionary, part of the WebRTC API, is used to describe the configuration parameters for a single media [codec](https://developer.mozilla.org/en-US/docs/Glossary/Codec). In addition to being the type of the <span class="page-not-created">`RTCRtpParameters.codecs`</span> property, it's used when calling [`RTCRtpTransceiver.setCodecPreferences()`](rtcrtptransceiver/setcodecpreferences) to configure a transceiver's codecs before beginning the offer/answer process to establish a WebRTC peer connection.

Most of the fields in this property take values which are defined and maintained by the Internet Assigned Numbers Authority (IANA). References to relevant IANA documents are provided in the [see also](#see_also) section at the end of this article.

Properties
----------

 <span class="page-not-created">`payloadType`</span> <span class="badge inline optional">Optional</span>   
The [RTP payload type](https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-1) used to identify this codec.

 <span class="page-not-created">`mimeType`</span> <span class="badge inline optional">Optional</span>   
The codec's MIME media type and subtype specified as a [`DOMString`](domstring) of the form `"type/subtype"`. IANA maintains a [registry of valid MIME types](https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-2).

 <span class="page-not-created">`clockRate`</span> <span class="badge inline optional">Optional</span>   
An unsigned long integer value specifying the codec's clock rate in hertz (Hz). The clock rate is the rate at which the codec's RTP timestamp advances. Most codecs have specific values or ranges of values they permit; see the [IANA payload format media type registry](https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-2) for details.

 <span class="page-not-created">`channels`</span> <span class="badge inline optional">Optional</span>   
An unsigned short integer indicating the number of channels the codec should support. For example, for audio codecs, a value of 1 specifies monaural sound while 2 indicates stereo.

 <span class="page-not-created">`sdpFmtpLine`</span> <span class="badge inline optional">Optional</span>   
A `DOMString` containing the format-specific parameters field from the `"a=fmtp"` line in the codec's [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP), if one is present; see [section 5.8 of the IETF specification for JSEP](https://datatracker.ietf.org/doc/html/draft-ietf-rtcweb-jsep-24#section-5.8).

**Note:** On an [`RTCRtpReceiver`](rtcrtpreceiver), the format-specific parameters come from the SDP sent by the remote peer, while for [`RTCRtpSender`](rtcrtpsender), they're provided by the local description.

See also
--------

[Real-Time Transport Protocol (RTP) Parameters](https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml)  
The IANA document providing registries of permitted values for the RTP parameters used by this dictionary.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpCodecParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpCodecParameters</a>
