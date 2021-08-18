MediaTrackSupportedConstraints.autoGainControl
==============================================

The [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary's `autoGainControl` property is a read-only Boolean value which is present (and set to `true`) in the object returned by [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints) if and only if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) supports the `autoGainControl` constraint. If the constraint isn't supported, it's not included in the list, so this value will never be `false`.

You can access the supported constraints dictionary by calling `navigator.mediaDevices.getSupportedConstraints()`.

The `autoGainControl` constraint indicates whether or not the browser offers the ability to automatically control the gain (volume) on media tracks; this obviously is contingent on whether or not the individual device supports automatic gain control as well; it's typically a feature provided by microphones.

Syntax
------

    autoGainSupported = supportedConstraintsDictionary.autoGainControl;

### Value

This property is present in the dictionary (and its value is always `true`) if the user agent supports the `autoGainControl` constraint. If the property isn't present, this property is missing from the supported constraints dictionary, and you'll get [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if you try to look at its value.

Example
-------

This example displays whether or not your browser supports the `autoGainControl` constraint.

    let result = document.getElementById("result");

    if (navigator.mediaDevices.getSupportedConstraints().autoGainControl) {
        result.textContent = "Supported!";
    } else {
        result.textContent = "Not supported!";
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksupportedconstraints-autogaincontrol">Media Capture and Streams<br />
<span class="small">The definition of 'autoGainControl' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`autoGainControl`

69

≤79

55

Yes-55

No

Yes

?

69

69

55

Yes-55

Yes

?

10.0

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
-   [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/autoGainControl" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/autoGainControl</a>
