RTCIceCandidateStats.address
============================

The `address` property of the [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary indicates the address of the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate. While it's preferred that the address be specified as an IPv4 or IPv6 numeric address, a fully-qualified domain name can be used as well. When a domain name is specified, the first IP address selected for that address is used, even if the domain name maps to multiple IP addresses.

Syntax
------

    candidateAddress = rtcIceCandidateStats.address;

### Value

Either an IPv4 or IPv6 address or a fully-qualified domain name, which corresponds to the candidate.

-   If the value of `address` is comprised entirely of digits from 0-9 with periods as separators, the value is interpreted as an IPv4 address.
-   If the value is entirely comprised of hexadecimal digits and colon (":") characters, it is interpreted as an IPv6 address.
-   Otherwise, the `address` is presumed to be a fully-qualified domain name, which is resolved first using an AAAA record (assuming IPv6 is available), then using an A record (if no result is found or the device onlu supports IPv4). If multiple IP addresses are returned in response to the query, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) selects one, which is then used for the duration of ICE processing.

Usage notes
-----------

The `address` property was previously known as `ip`, and only permitted IPv4 and IPv6 addresses to be used. The addition of support for fully-qualified domain names to be used for the address brought about the renaming of the property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-address">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.address' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`address`

No

No

65

27

No

?

?

No

No

65

27

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/address" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/address</a>
