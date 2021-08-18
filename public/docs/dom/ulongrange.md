ULongRange
==========

The `ULongRange` dictionary is used to define a range of permitted integer values for a property, with either or both a maximum and minimum value specified. The <span class="page-not-created">`ConstrainULongRange`</span> dictionary is based on this, augmenting it to support exact and ideal values as well.

Properties
----------

`max`  
A numeric value in the range of signed 32-bit integers, specifying the largest permissible value of the property it describes.

`min`  
A numeric value in the range of signed 32-bit integers, specifying the smallest permissible value of the property it describes.

The specified `min` and/or and `max` values are *required*. If no match can be found that is within the given range, an error will occur.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-ulongrange">Media Capture and Streams<br />
<span class="small">The definition of 'ULongRange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`ULongRange`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [Media Capture and Streams API](media_streams_api)
-   [Capabilities, constraints, and settings](media_streams_api/constraints)
-   <span class="page-not-created">`ConstrainULongRange`</span>
-   [`MediaTrackConstraints`](mediatrackconstraints)
-   <span class="page-not-created">`MediaTrackCapabilities`</span>
-   [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ULongRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ULongRange</a>
