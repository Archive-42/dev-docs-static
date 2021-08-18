PhotoCapabilities.redEyeReduction
=================================

The `redEyeReduction` read-only property of the [`PhotoCapabilities`](../photocapabilities) interface returns an enum indicating the red-eye reduction capability of the source.

Syntax
------

    const redEyeReduction = photoCapabilities.redEyeReduction

### Value

One of `"never"`, `"always"`, or `"controllable"`.

`never`  
Red-eye reduction is not available.

`always`  
Red-eye reduction is available in the source and it is always turned on.

`controllable`  
Red-eye reduction is available in the source and it is configurable via the <span class="page-not-created">`PhotoSettings`</span> object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-photocapabilities-redeyereduction">MediaStream Image Capture<br />
<span class="small">The definition of 'redEyeReduction' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`redEyeReduction`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities/redEyeReduction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities/redEyeReduction</a>
