# RTCIceCandidatePairStats

The WebRTC `RTCIceCandidatePairStats` dictionary reports statistics which provide insight into the quality and performance of an [`RTCPeerConnection`](rtcpeerconnection) while connected and configured as described by the specified pair of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates.

If a [`RTCStats`](rtcstats)-based object's [`type`](rtcstats/type) is `candidate-pair`, it's an `RTCIceCandidatePairStats` object.

## Properties

_`RTCIceCandidatePairStats` is based upon [`RTCStats`](rtcstats) and inherits its properties. In addition, it adds the following new properties:_

[`availableIncomingBitrate`](rtcicecandidatepairstats/availableincomingbitrate) <span class="badge inline optional">Optional</span>  
Provides an informative value representing the available inbound capacity of the network by reporting the total number of bits per second available for all of the candidate pair's incoming [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) streams. This does not take into account the size of the <span class="page-not-created">IP</span> overhead, nor any other transport layers such as [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) or [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP).

[`availableOutgoingBitrate`](rtcicecandidatepairstats/availableoutgoingbitrate) <span class="badge inline optional">Optional</span>  
Provides an informative value representing the available outbound capacity of the network by reporting the total number of bits per second available for all of the candidate pair's outoing [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) streams. This does not take into account the size of the <span class="page-not-created">IP</span> overhead, nor any other transport layers such as [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) or [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP).

[`bytesReceieved`](rtcicecandidatepairstats/bytesreceived) <span class="badge inline optional">Optional</span>  
The total number of payload bytes received (that is, the total number of bytes received minus any headers, padding, or other administrative overhead) on this candidate pair so far.

[`bytesSent`](rtcicecandidatepairstats/bytessent) <span class="badge inline optional">Optional</span>  
The total number of payload bytes sent (that is, the total number of bytes sent minus any headers, padding, or other administrative overhead) so far on this candidate pair.

[`circuitBreakerTriggerCount`](rtcicecandidatepairstats/circuitbreakertriggercount) <span class="badge inline optional">Optional</span>  
An integer value indicating the number of times the circuit-breaker has been triggered for this particular 5-tuple (the set of five values comprising a TCP connection: source IP address, source port number, destination IP address, destination port number, and protocol). The circuit breaker is triggered whenever a connection times out or otherwise needs to be automatically aborted.

[`consentExpiredTimestamp`](rtcicecandidatepairstats/consentexpiredtimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value indicating the time at which the most recent STUN binding response expired. This value is `undefined` if no valid STUN binding responses have been sent on the candidate pair; this can only happen if [`responsesReceived`](rtcicecandidatepairstats/responsesreceived) is 0.

[`consentRequestsSent`](rtcicecandidatepairstats/consentrequestssent) <span class="badge inline optional">Optional</span>  
The total number of consent requests that have been sent on this candidate pair.

[`currentRoundTripTime`](rtcicecandidatepairstats/currentroundtriptime) <span class="badge inline optional">Optional</span>  
A floating-point value indicating the total time, in seconds, that elapsed between the most recently-sent STUN request and the response being received. This may be based upon requests that were involved in confirming permission to open the connection.

[`firstRequestTimestamp`](rtcicecandidatepairstats/firstrequesttimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value which specifies the time at which the first STUN request was sent from the local peer to the remote peer for this candidate pair.

[`lastPacketReceivedTimestamp`](rtcicecandidatepairstats/lastpacketreceivedtimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value indicating the time at which the last packet was received by the local peer from the remote peer for this candidate pair. Timestamps are not recorded for STUN packets.

[`lastPacketSentTimestamp`](rtcicecandidatepairstats/lastpacketsenttimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value indicating the time at which the last packet was sent from the local peer to the remote peer for this candidate pair. Timestamps are not recorded for STUN packets.

[`lastRequestTimestamp`](rtcicecandidatepairstats/lastrequesttimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value which specifies the time at which the last (most recent) STUN request was sent from the local peer to the remote peer for this candidate pair.

[`lastResponseTimestamp`](rtcicecandidatepairstats/lastresponsetimestamp) <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) value that specifies the time at which the last (most recent) STUN response was received by the local candidate from the remote candidate in this pair.

[`localCandidateId`](rtcicecandidatepairstats/localcandidateid) <span class="badge inline optional">Optional</span>  
The unique ID string corresponding to the [`RTCIceCandidate`](rtcicecandidate) from the data included in the [`RTCIceCandidateStats`](rtcicecandidatestats) object providing statistics for the candidate pair's local candidate.

[`nominated`](rtcicecandidatepairstats/nominated) <span class="badge inline optional">Optional</span>  
A Boolean value which, if `true`, indicates that the candidate pair described by this object is one which has been proposed for use, and will be (or was) used if its priority is the highest among the nominated candidate pairs. See [RFC 5245, section 7.1.3.2.4](https://tools.ietf.org/html/rfc5245#section-7.1.3.2.4) for details.

[`packetsReceived`](rtcicecandidatepairstats/packetsreceived) <span class="badge inline optional">Optional</span>  
The total number of packets received on this candidate pair.

[`packetsSent`](rtcicecandidatepairstats/packetssent) <span class="badge inline optional">Optional</span>  
The total number of packets sent on this candidate pair.

[`remoteCandidateId`](rtcicecandidatepairstats/remotecandidateid) <span class="badge inline optional">Optional</span>  
The unique ID string corresponding to the remote candidate from which data was taken to construct the `RTCIceCandidateStats` object describing the remote end of the connection.

[`requestsReceived`](rtcicecandidatepairstats/requestsreceived) <span class="badge inline optional">Optional</span>  
The total number of connectivity check requests that have been received, including retransmissions. This value includes both connectivity checks and STUN consent checks.

[`requestsSent`](rtcicecandidatepairstats/requestssent) <span class="badge inline optional">Optional</span>  
The total number of connectivity check requests that have been sent, _not_ including retransmissions.

[`responsesReceived`](rtcicecandidatepairstats/responsesreceived) <span class="badge inline optional">Optional</span>  
The total number of connectivity check responses that have been received.

[`responsesSent`](rtcicecandidatepairstats/responsessent) <span class="badge inline optional">Optional</span>  
The total number of connectivity check responses that have been sent. This includes both connectivity check requests and STUN consent requests.

[`retransmissionsReceived`](rtcicecandidatepairstats/retransmissionsreceived) <span class="badge inline optional">Optional</span>  
The total number of times connectivity check request retransmissions were received. A retransmission is a connectivity check request whose `TRANSACTION_TRANSMIT_COUNTER` attribute's `req` field is greater than 1.

[`retransmissionsSent`](rtcicecandidatepairstats/retransmissionssent) <span class="badge inline optional">Optional</span>  
The total number of times connectivity check request retransmissions were sent.

[`state`](rtcicecandidatepairstats/state) <span class="badge inline optional">Optional</span>  
A [`RTCStatsIceCandidatePairState`](rtcstatsicecandidatepairstate) object which indicates the state of the connection between the two candidates.

[`totalRoundTripTime`](rtcicecandidatepairstats/totalroundtriptime) <span class="badge inline optional">Optional</span>  
A floating-point value indicating the total time, in seconds, that has elapsed between sending STUN requests and receiving responses to them, for all such requests made to date on this candidate pair. This includes botyh connectivity check and consent check requests. You can compute the average round trip time (RTT) by dividing this value by [`responsesReceived`](rtcicecandidatepairstats/responsesreceived).

[`transportId`](rtcicecandidatepairstats/transportid) <span class="badge inline optional">Optional</span>  
A [`DOMString`](domstring) that uniquely identifies the [`RTCIceTransport`](rtcicetransport) that was inspected to obtain the transport-related statistics (as found in <span class="page-not-created">`RTCTransportStats`</span>) used in generating this object.

### Obsolete properties

The following properties have been removed from the specification and should no longer be used. You should update any existing code to avoid using them as soon as is practical. Check the [compatibility table](#browser_compatibility) for details on which browsers support them and in which versions.

[`priority`](rtcicecandidatepairstats/priority) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline optional">Optional</span>  
An integer value indicating the candidate pair's priority.

[`readable`](rtcicecandidatepairstats/readable) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline optional">Optional</span>  
A Boolean value indicating whether or not data can be sent over the connection described by the candidate pair.

[`writable`](rtcicecandidatepairstats/writable) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline optional">Optional</span>  
A Boolean value indicating whether or not data can be received on the connection described by the candidate pair.

### Non-standard properties

[`selected`](rtcicecandidatepairstats/selected) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline optional">Optional</span>  
A Firefox-specific Boolean value which is `true` if the candidate pair described by this object is the one currently in use. The spec-compliant way to determine the selected candidate pair is to look for a stats object of type `transport`, which is an <span class="page-not-created">`RTCTransportStats`</span> object. That object's <span class="page-not-created">`selectedCandidatePairId`</span> property indicates whether or not the specified transport is the one being used.

## Usage notes

The currently-active ICE candidate pair—if any—can be obtained by calling the [`RTCIceTransport`](rtcicetransport) method [`getSelectedCandidatePair()`](rtcicetransport/getselectedcandidatepair), which returns an [`RTCIceCandidatePair`](rtcicecandidatepair) object, or `null` if there isn't a pair selected. The active candidate pair describes the current configuration of the two ends of the [`RTCPeerConnection`](rtcpeerconnection).

Any candidate pair that isn't the active pair of candidates for a transport gets deleted if the [`RTCIceTransport`](rtcicetransport) performs an ICE restart, at which point the [`state`](rtcicetransport/state) of the ICE transport returns to `new` and negotiation starts once again. For more information, see [ICE restart](webrtc_api/session_lifetime#ice_restart) in [Lifetime of a WebRTC session](webrtc_api/session_lifetime).

## Example

This example computes the average time elapsed between connectivity checks if the [`RTCStats`](rtcstats) object `rtcStats` is an `RTCIceCandidatePairStats` object.

    if (rtcStats && rtcStats.type === "candidate-pair") {
      let elapsed = (rtcStats.lastRequestTimestamp - rtcStats.firstRequestTimestamp)
                      / rtcStats.requestsSent;

      log("Average time between ICE connectivity checks: " + elapsed + " ms.");
    }

The code begins by looking at `rtcStats` to see if its [`type`](rtcstats/type) is `candidate-pair`. If it is, then we know that `rtcStats` is in fact an [`RTCIceCandidatePairStats`](rtcicecandidatepairstats) object. If so, we compute the average time elapsed between STUN connectivity checks and log that information.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`RTCIceCandidatePairStats`

56

≤79

29

No

?

?

56

56

29

?

?

6.0

`availableIncomingBitrate`

No

No

No

No

?

?

No

No

No

?

?

No

`availableOutgoingBitrate`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

`bytesReceived`

Yes

≤79

56

No

?

?

Yes

Yes

56

?

?

Yes

`bytesSent`

Yes

≤79

56

No

?

?

Yes

Yes

56

?

?

Yes

`circuitBreakerTriggerCount`

No

No

No

No

?

?

No

No

No

?

?

No

`consentExpiredTimestamp`

No

No

No

No

?

?

No

No

No

?

?

No

`consentRequestsSent`

No

No

No

No

?

?

No

No

No

?

?

No

`currentRoundTripTime`

71

Yes

≤79

≤79

No

No

?

?

71

Yes

71

Yes

No

?

?

10.0

Yes

`firstRequestTimeStamp`

No

No

No

No

?

?

No

No

No

?

?

No

`lastPacketReceivedTimestamp`

No

No

56

No

?

?

No

No

56

?

?

No

`lastPacketSentTimestamp`

No

No

56

No

?

?

No

No

56

?

?

No

`lastReponseTimestamp`

No

No

No

No

?

?

No

No

No

?

?

No

`lastRequestTimestamp`

No

No

No

No

?

?

No

No

No

?

?

No

`localCandidateId`

No

No

29

No

?

?

No

No

29

?

?

No

`nominated`

No

No

56

No

?

?

No

No

56

?

?

No

`packetsReceived`

No

No

No

No

?

?

No

No

No

?

?

No

`packetsSent`

No

No

No

No

?

?

No

No

No

?

?

No

`priority`

No

No

42

29

No

?

?

No

No

42

29

?

?

No

`readable`

No

No

56

No

?

?

No

No

56

?

?

No

`remoteCandidateId`

No

No

29

No

?

?

No

No

29

?

?

No

`requestsReceived`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

`requestsSent`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

`responsesReceived`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

`responsesSent`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

`retransmissionsReceived`

No

No

No

No

?

?

No

No

No

?

?

No

`retransmissionsSent`

No

No

No

No

?

?

No

No

No

?

?

No

`state`

No

No

29

No

?

?

No

No

29

?

?

No

`totalRoundTripTime`

71

Yes

≤79

≤79

No

No

?

?

No

71

Yes

No

?

?

10.0

Yes

`transportId`

No

No

56

29

No

?

?

No

No

56

29

?

?

No

`writable`

Yes

Chrome does not currently use the specification's algorithm to determine the value of `writable`; it may not match the behavior of other browsers.

≤79

Edge does not currently use the specification's algorithm to determine the value of `writable`; it may not match the behavior of other browsers.

56

No

?

?

Yes

Yes

Chrome does not currently use the specification's algorithm to determine the value of `writable`; it may not match the behavior of other browsers.

56

?

?

Yes

Samsung Internet does not currently use the specification's algorithm to determine the value of `writable`; it may not match the behavior of other browsers.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats</a>
