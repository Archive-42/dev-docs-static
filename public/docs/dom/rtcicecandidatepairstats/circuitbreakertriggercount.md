# RTCIceCandidatePairStats.circuitBreakerTriggerCount

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `circuitBreakerTriggerCount` indicates the number of times the circuit-breaker has been triggered to indicate a connection timeout or other unexpected connection abort on this specific connection configuration.

A circuit breaker trigger is fired each time the connection times out or otherwise needs to be halted automatically.

## Syntax

    cbtCount = rtcIceCandidatePairStats.circuitBreakerTriggerCount;

### Value

An integer value indicating the number of times the circuit-breaker has been triggered for the 5-tuple used by this connection. A 5-tuple defining a TCP connection is made up of the following data:

- The source IP address.
- The source port number.
- The destination IP address.
- The destination port number.
- Network protocol.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-circuitbreakertriggercount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.circuitBreakerTriggerCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/circuitBreakerTriggerCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/circuitBreakerTriggerCount</a>
