OverconstrainedError.OverconstrainedError()
===========================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OverconstrainedError` constructor creates a new [`OverconstrainedError`](../overconstrainederror) object which indicates that the set of desired capabilities for the current [`MediaStreamTrack`](../mediastreamtrack) cannot currently be met. When this event is thrown on a `MediaStreamTrack`, it is muted until either the current constraints can be established or until satisfiable constraints are applied.

Syntax
------

    var OverconstrainedError = new OverconstrainedError()

### Parameters

constraint  
The constraint that was not satified.

message  
Text for the error's `message` property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-overconstrainederror-constructor">Media Capture and Streams<br />
<span class="small">The definition of 'OverconstrainedError()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OverconstrainedError`

63

79

?

No

50

11

63

63

?

46

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OverconstrainedError/OverconstrainedError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OverconstrainedError/OverconstrainedError</a>
