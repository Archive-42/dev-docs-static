# RTCIceCandidatePairStats.writable

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The _obsolete_ [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `writable` reports whether or not the connection described by the candidate pair is writable.

## Syntax

    isWritable = rtcIceCandidatePairStats.writable;

### Value

A Boolean value which is `true` if the connection described by this candidate pair has received acknowledgement of receipt (ACK) for at least one ICE request _and_ that [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) consent hasn't expired.

**Note:** This property was removed from the specification in early 2017 because you can determine whether or not an incoming ICE request is available to read by checking to see if [`responsesReceived`](responsesreceived) is greater than 0 and that the time specified by [`consentExpiredTimestamp`](consentexpiredtimestamp) has not passed:

    if (icpStats.responsesReceived > 0
        && icpStats.consentExpiredTimestamp < performance.now()) {
      /* at least one ICE response has been received */
    }

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/writable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/writable</a>
