# MediaRecorder.ignoreMutedMedia

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `ignoreMutedMedia` property of the [`MediaRecorder`](../mediarecorder) interface indicates whether the `MediaRecorder` instance will record input, when the input MediaStreamTrack is muted. If this attribute is `false`, MediaRecorder will record silence for audio and black frames for video. The default is `false`.

## Syntax

    var boolean = MediaRecorder.ignoreMutedMedia
    MediaRecorder.ignoreMutedMedia = boolean

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

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

`ignoreMutedMedia`

49-57

No

No

No

36-44

No

49-57

49-57

No

36-44

No

5.0-7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ignoreMutedMedia" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ignoreMutedMedia</a>
