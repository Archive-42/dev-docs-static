# MediaTrackSupportedConstraints.frameRate

The [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary's `frameRate` property is a read-only Boolean value which is present (and set to `true`) in the object returned by [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints) if and only if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) supports the [`frameRate`](../mediatrackconstraints/framerate) constraint. If the constraint isn't supported, it's not included in the list, so this value will never be `false`.

The `frameRate` constraint can be used to establish acceptable upper and lower bounds on the video frame rate for a new video track, or to specify an exact frame rate that must be provided for the request to succeed. Checking the value of this property lets you determine if the user agent allows constraining the video track configuration by frame rate. See the [example](#example) to see how this can be used.

## Syntax

    frameRateConstraintSupported = supportedConstraintsDictionary.frameRate;

### Value

This property is present in the dictionary if the user agent supports the `frameRate` constraint. If the property isn't present, the user agent doesn't allow specifying limits on the frame rate for video tracks.

If this property is present, its value is always `true`.

## Example

This simple example looks to see if your browser supports constraining the frame rate when requesting video tracks.

### JavaScript

    let result = document.getElementById("result");

    if (navigator.mediaDevices.getSupportedConstraints().frameRate) {
        result.textContent = "Supported!";
    } else {
        result.textContent = "Not supported!";
    }

### HTML

    <div id="result">
    </div>

### CSS

    #result {
      font: 14px "Arial", sans-serif;
    }

### Result

The output, showing if your browser supports the `frameRate` constraint, is:

While this example is trivial, you can replace the simple output of "Supported" vs. "Not supported" with code to provide alternative methods for presenting the audiovisual information you want to share with the user or otherwise work with.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksupportedconstraints-framerate">Media Capture and Streams<br />
<span class="small">The definition of 'frameRate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`frameRate`

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

## See also

- [Media Capture and Streams API](../media_streams_api)
- [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
- [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
- [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/frameRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/frameRate</a>
