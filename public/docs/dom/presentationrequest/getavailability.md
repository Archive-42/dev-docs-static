# PresentationRequest.getAvailability()

When the `getAvailability()` method is called, the user agent _MUST_ run the following steps:

Input  
presentationUrls, a list of [presentation request URLs](https://www.w3.org/TR/presentation-api/#dfn-presentation-request-urls)

Output  
P, a [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise)

1.  If one of the following conditions is true:

    - The result of running the [prohibits mixed security contexts algorithm](https://www.w3.org/TR/presentation-api/#dfn-prohibits-mixed-security-contexts-algorithm) on the document's [settings object](https://www.w3.org/TR/presentation-api/#dfn-settings-object) is `"Prohibits Mixed Security Contexts"` and presentationUrl is an [a priori unauthenticated URL](https://www.w3.org/TR/presentation-api/#dfn-a-priori-unauthenticated-url).
    - The document object's [active sandboxing flag set](https://www.w3.org/TR/presentation-api/#dfn-active-sandboxing-flag-set) has the [sandboxed presentation browsing context flag](https://www.w3.org/TR/presentation-api/#sandboxed-presentation-browsing-context-flag) set.

    Run the following substeps:

    1.  Return a [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise) rejected with a [`SecurityError`](https://www.w3.org/TR/presentation-api/#dfn-securityerror).
    2.  Abort these steps.

2.  Let P be a new [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise).
3.  Return P, but continue running these steps [in parallel](https://www.w3.org/TR/presentation-api/#dfn-in-parallel).
4.  If the user agent is unable to [monitor the list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-monitor-the-list-of-available-presentation-displays) for the entire duration of the [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context) (e.g., because the user has disabled this feature), then:
    1.  [Resolve](https://www.w3.org/TR/presentation-api/#dfn-resolving-a-promise) P with a new `PresentationAvailability` object with its `value` property set to `false`.
    2.  Abort all the remaining steps.
5.  If the user agent is unable to continuously [monitor the list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-monitor-the-list-of-available-presentation-displays) but can find presentation displays in order to start a connection, then:
    1.  [Reject](https://www.w3.org/TR/presentation-api/#dfn-rejecting-a-promise) P with a [`NotSupportedError`](https://www.w3.org/TR/presentation-api/#dfn-notsupportederror) exception.
    2.  Abort all the remaining steps.
6.  If there exists a tuple _(A, presentationUrls)_ in the [set of availability objects](https://www.w3.org/TR/presentation-api/#dfn-set-of-availability-objects), then:
    1.  [Resolve](https://www.w3.org/TR/presentation-api/#dfn-resolving-a-promise) P with A.
    2.  Abort all the remaining steps.
7.  Let A be a new `PresentationAvailability` object with its `value` property set as follows:
    1.  `false` if the [list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-list-of-available-presentation-displays) is empty.
    2.  `true` if there is at least one [compatible presentation display](https://www.w3.org/TR/presentation-api/#dfn-compatible-presentation-display) for some member of presentationUrls. Meaning there is an entry (presentationUrl, display) in the [list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-list-of-available-presentation-displays) for some presentationUrl in presentationUrls.
    3.  `false` otherwise.
8.  Create a tuple _(A, presentationUrls)_ and add it to the [set of availability objects](https://www.w3.org/TR/presentation-api/#dfn-set-of-availability-objects).
9.  Run the algorithm to [monitor the list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-monitor-the-list-of-available-presentation-displays).
10. [Resolve](https://www.w3.org/TR/presentation-api/#dfn-resolving-a-promise) P with A.

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

`getAvailability`

48

≤79

51-88

No

35

No

No

48

51-79

35

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/getAvailability" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/getAvailability</a>
