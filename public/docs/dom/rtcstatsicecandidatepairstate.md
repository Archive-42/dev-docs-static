RTCStatsIceCandidatePairState
=============================

The `RTCStatsIceCandidatePairState` enumerated type represents the set of string values which are possible for the [`RTCIceCandidatePairStats`](rtcicecandidatepairstats) object's [`state`](rtcicecandidatepairstats/state) property. This represents the state of this candidate pair within the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) check list for the [`RTCPeerConnection`](rtcpeerconnection).

See [ICE check lists](rtcicecandidatepairstats/state#ice_check_lists) in [`RTCIceCandidatePairStats.state`](rtcicecandidatepairstats/state) for further information about how ICE check lsits work.

Values
------

`failed`  
A check for this pair has been performed but failed. A failure can occur either because no response was received or because the response indicated that an unrecoverable error occurred.

`frozen`  
No check has been performed yet for this candidate pair, and performing the check is blocked until another check is successful. Once that check has succeeded, this pair will unfreeze and move into the `waiting` state.

`in-progress`  
A check has been initiated for this pair, but the check's transaction is still in progress.

`succeeded`  
A check for this pair has been completed successfully.

`waiting`  
This pair has not yet been checked, but the check can be performed as soon as this pair is the highest priority pair remaining in the `waiting` state.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#rtcstatsicecandidatepairstate-enum">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCStatsIceCandidatePairState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStatsIceCandidatePairState`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsIceCandidatePairState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsIceCandidatePairState</a>
