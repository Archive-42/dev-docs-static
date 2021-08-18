# MediaStream.ended

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `ended` read-only property of the [`MediaStream`](../mediastream) interface returns a Boolean value which is `true` if the stream has been completely read, or `false` if the end of the stream has not been reached. This value once the `ended` event has been fired.

This property has been removed from the specification; you should instead rely on the `ended` event or check the value of [`MediaStreamTrack.readyState`](../mediastreamtrack/readystate) to see if its value is `"ended"` for the track or tracks you want to ensure have finished playing.

## Syntax

    var hasEnded = MediaStream.ended;

### Value

A Boolean value that returns `true` if the end of the stream has been reached.

## Specifications

No longer part of any specification. This property was part of earlier drafts of the [Media Capture and Streams specification](https://www.w3.org/TR/mediacapture-streams).

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

`ended`

Yes-54

Deprecated in Chrome 52.

No

No

No

Yes-39

No

Yes-54

Deprecated in Chrome 52.

Yes-54

Deprecated in Chrome 52.

No

Yes-41

No

Yes-6.0

Deprecated in Samsung Internet 6.0.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/ended" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/ended</a>
