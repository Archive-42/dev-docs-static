MediaTrackSupportedConstraints.facingMode
=========================================

The [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary's `facingMode` property is a read-only Boolean value which is present (and set to `true`) in the object returned by [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints) if and only if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) supports the `facingMode` constraint. If the constraint isn't supported, it's not included in the list, so this value will never be `false`.

You can access the supported constraints dictionary by calling `navigator.mediaDevices.getSupportedConstraints()`.

Syntax
------

    facingModeConstraintSupported = supportedConstraintsDictionary.facingMode;

### Value

This property is present in the dictionary (and its value is always `true`) if the user agent supports the `facingMode` constraint. If the property isn't present, this property is missing from the supported constraints dictionary, and you'll get [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if you try to look at its value.

Example
-------

    let result = document.getElementById("result");

    if (navigator.mediaDevices.getSupportedConstraints().facingMode) {
        result.textContent = "Supported!";
    } else {
        result.textContent = "Not supported!";
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksupportedconstraints-facingmode">Media Capture and Streams<br />
<span class="small">The definition of 'facingMode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`facingMode`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
-   [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/facingMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/facingMode</a>
