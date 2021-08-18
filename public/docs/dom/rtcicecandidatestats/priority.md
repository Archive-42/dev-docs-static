RTCIceCandidateStats.priority
=============================

The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `priority` property is a positive integer value indicating the priority (or desirability) of the described candidate. During [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) negotiation while setting up a WebRTC peer connection, the priority values reported to the remote peer by a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) are used to determine which candidates are considered "more desirable". The higher the value, the more desirable the candidate is.

Syntax
------

    priority = rtcIceCandidateStats.priority;

### Value

A positive integer indicating the priority of the [`RTCIceCandidate`](../rtcicecandidate) described by the `RTCIceCandidateStats` object. The value may be anywhere from 1 to 2,147,483,647.

Determining priority
--------------------

The ICE specification describes how user agents and other software using WebRTC should calculate the priority. The priority of a candidate is calculated using the following variables as inputs:

-   The preferability of the candidate type (local, server reflexive, peer reflexive, or relayed)
-   The preferability of the candidate's specific IP address (for multihomed agents)
-   The candidate's component ID (1 for RTP, 2 for RTCP)

The candidate's priority is computed using the formula (*p<sub>type</sub>* is the priority of the candidate's type and *p<sub>local</sub>* is the priority of the IP address):

*p**r**i**o**r**i**t**y* = 2<sup>24</sup> × *p*<sub>*t**y**p**e*</sub> + 2<sup>8</sup> × *p*<sub>*l**o**c**a**l*</sub> + (256 − *c**o**m**p**o**n**e**n**t**I**D*)

This is equivalent to mapping the priorities of teh candidate type, the local IP, and the component ID into various bit ranges within the 32-bit `priority` value.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-port">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.port' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`priority`

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

See also
--------

-   [RFC 5245: 4.1.2.1](https://tools.ietf.org/html/rfc5245): Recommended Formula section in the ICE specification

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/priority" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/priority</a>
