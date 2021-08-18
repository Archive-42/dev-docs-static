XRSession.requestReferenceSpace()
=================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `requestReferenceSpace()` method of the [`XRSession`](../xrsession) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of either [`XRReferenceSpace`](../xrreferencespace) or [`XRBoundedReferenceSpace`](../xrboundedreferencespace) as appropriate given the type of reference space requested.

Syntax
------

    refSpacePromise = xrSession.requestReferenceSpace(referenceSpaceType);

### Parameters

`type`  
A [`DOMString`](../domstring) specifying the type of reference space for which an instance is to be returned. The string must be one of those found in the [`XRReferenceSpaceType`](../xrreferencespacetype) enumerated type.

The reference space returned by [`XRSession.requestReferenceSpace()`](requestreferencespace) is either [`XRReferenceSpace`](../xrreferencespace) or [`XRBoundedReferenceSpace`](../xrboundedreferencespace). The "Interface" column in the table below indicates which of the two types is returned for each reference space type constant..

### Reference space descriptors

The types of reference space are listed in the table below, with brief information about their use cases and which interface is used to implement them.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>XRReferenceSpaceType</th><th>Description</th><th>Interface</th></tr></thead><tbody><tr class="odd"><td><span id="bounded-floor"><code>bounded-floor</code></span></td><td>Similar to the <code>local</code> type, except the user is not expected to move outside a predetermined boundary, given by the <a href="../xrboundedreferencespace/boundsgeometry"><code>boundsGeometry</code></a> in the returned object.</td><td><a href="../xrboundedreferencespace"><code>XRBoundedReferenceSpace</code></a></td></tr><tr class="even"><td><span id="local"><code>local</code></span></td><td><p>A tracking space whose native origin is located near the viewer's position at the time the session was created. The exact position depends on the underlying platform and implementation. The user isn't expected to move much if at all beyond their starting position, and tracking is optimized for this use case.</p><p>For devices with six degrees of freedom (6DoF) tracking, the <code>local</code> reference space tries to keep the origin stable relative to the environment.</p></td><td><a href="../xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="odd"><td><span id="local-floor"><code>local-floor</code></span></td><td>Similar to the <code>local</code> type, except the starting position is placed in a safe location for the viewer to stand, where the value of the y axis is 0 at floor level. If that floor level isn't known, the <a href="https://developer.mozilla.org/en-US/docs/Glossary/User_agent">user agent</a> will estimate the floor level. If the estimated floor level is non-zero, the browser is expected to round it such a way as to avoid fingerprinting (likely to the nearest centimeter).</td><td><a href="../xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="even"><td><span id="unbounded"><code>unbounded</code></span></td><td>A tracking space which allows the user total freedom of movement, possibly over extremely long distances from their origin point. The viewer isn't tracked at all; tracking is optimized for stability around the user's current position, so the native origin may drift as needed to accommodate that need.</td><td><a href="../xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="odd"><td><span id="viewer"><code>viewer</code></span></td><td>A tracking space whose native origin tracks the viewer's position and orientation. This is used for environments in which the user can physically move around, and is supported by all instances of <a href="../xrsession"><code>XRSession</code></a>, both immersive and inline, though it's most useful for inline sessions. It's particularly useful when determining the distance between the viewer and an input, or when working with offset spaces. Otherwise, typically, one of the other reference space types will be used more often.</td><td><a href="../xrreferencespace"><code>XRReferenceSpace</code></a></td></tr></tbody></table>

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an [`XRReferenceSpace`](../xrreferencespace) object.

### Exceptions

Rather than throwing true exceptions, `requestReferenceSpace()` rejects the returned promise with a [`DOMException`](../domexception) whose name is found in the list below:

`NotSupportedError`  
The requested reference space is not supported.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-requestreferencespace">WebXR Device API<br />
<span class="small">The definition of 'requestReferenceSpace()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`requestReferenceSpace`

79

79

No

No

No

No

No

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/requestReferenceSpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/requestReferenceSpace</a>
