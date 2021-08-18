PresentationAvailability
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

A `PresentationAvailability` object is associated with available [presentation displays](https://www.w3.org/TR/presentation-api/#dfn-presentation-display) and represents the presentation display availability for a presentation request. If the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) can [monitor the list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-monitor-the-list-of-available-presentation-displays) in the background (without a pending request to `start()`), the `PresentationAvailability` object *MUST* be implemented in a [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context).

The `value` attribute *MUST* return the last value it was set to. The value is updated by the [monitor the list of available presentation displays](https://www.w3.org/TR/presentation-api/#dfn-monitor-the-list-of-available-presentation-displays) algorithm.

The `onchange` attribute is an [event handler](https://www.w3.org/TR/presentation-api/#dfn-event-handler) whose corresponding [event handler event type](https://www.w3.org/TR/presentation-api/#dfn-event-handler-event-type) is `change`.

Properties
----------

 [`PresentationAvailability.value`](presentationavailability/value) <span class="badge inline readonly">Read only </span>   
A boolean value indicating whether the given presentation display is available. The `value` attribute *MUST* return the last value it was set to.

### Event handlers

[`PresentationAvailability.onchange`](presentationavailability/onchange)  
Indicates that the availability of the presentation display has changed.

Methods
-------

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationavailability">Presentation API<br />
<span class="small">The definition of 'PresentationAvailability interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationAvailability`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`onchange`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`value`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationAvailability" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationAvailability</a>
