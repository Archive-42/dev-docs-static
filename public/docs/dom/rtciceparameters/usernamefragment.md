RTCIceParameters.usernameFragment
=================================

The **[`RTCIceParameters`](../rtciceparameters)** dictionary's `usernameFragment` property specifies the username fragment ("ufrag") that uniquely identifies the corresponding ICE session for the duration of the current ICE session.

Syntax
------

    ufrag = RTCIceParameters.usernameFragment;

### Value

A [`DOMString`](../domstring) containing the username fragment that, in tandem with the [`password`](password), uniquely identify the ICE session being used by the transport. The string may be up to 256 characters long.

See [`RTCIceCandidate.usernameFragment`](../rtcicecandidate/usernamefragment) to learn more about username fragments and their role in a connection.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtciceparameters-usernamefragment">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceParameters.usernameFragment' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCIceParameters.usernameFragment`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters/usernameFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters/usernameFragment</a>
