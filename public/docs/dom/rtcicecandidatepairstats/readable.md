RTCIceCandidatePairStats.readable
=================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The *obsolete* [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `readable` reports whether or not the connection described by the candidate pair has received at least one valid incoming ICE request.

Syntax
------

    isReadable = rtcIceCandidatePairStats.readable;

### Value

A Boolean value which is `true` if the connection described by this candidate pair has received at least one valid ICE request, and is therefore ready to be read from.

**Note:** This property was removed from the specification in early 2017 because you can determine whether or not the connection is readable by checking to see if [`requestsReceived`](requestsreceived) is greater than 0:

    if (icpStats.requestsReceived > 0) {
      /* at least one ICE request has been received */
    }

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/readable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/readable</a>
