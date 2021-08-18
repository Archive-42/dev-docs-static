LayoutShiftAttribution
======================

The `LayoutShiftAttribution` interface of the Layout Instability API provides debugging information about elements which have shifted.

Properties
----------

`LayoutShiftAttribution.Node`  
Returns the element that has shifted (null if it has been removed).

`LayoutShiftAttribution.previousRect`  
Returns a [DOMRect](domrect) representing the position of the element before the shift.

`LayoutShiftAttribution.currentRect`  
Returns a [DOMRect](domrect) representing the position of the element after the shift.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/layout-instability/#layoutshiftattribution">Layout Instability API<br />
<span class="small">The definition of 'LayoutShiftAttribution' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`LayoutShiftAttribution`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`currentRect`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`node`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`previousRect`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`toJSON`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LayoutShiftAttribution" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LayoutShiftAttribution</a>
