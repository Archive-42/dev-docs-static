XREye
=====

The `XREye` enumerated type is used to identify which eye a particular [`XRView`](xrview) represents: `left` or `right`; or, if the view doesn't represent a single eye, the value may be `none`.

Values
------

`left`  
The [`XRView`](xrview) represents the point-of-view of the viewer's left eye.

`right`  
The view represents the viewer's right eye.

`none`  
The `XRView` describes a monoscopic view, or the view otherwise doesn't represent a particular eye's point-of-view.

Usage notes
-----------

These values are used by the [`XRView`](xrview) property [`eye`](xrview/eye).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#enumdef-xreye">WebXR Device API<br />
<span class="small">The definition of 'XREye' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XREye`

79

79

No

No

No

No

79

79

No

No

No

11.2

`left`

79

79

No

No

No

No

79

79

No

No

No

11.2

`none`

79

79

No

No

No

No

79

79

No

No

No

11.2

`right`

79

79

No

No

No

No

79

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XREye" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XREye</a>
