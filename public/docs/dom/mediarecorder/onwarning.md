# MediaRecorder.onwarning

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MediaRecorder.onwarning `event handler (part of the [MediaRecorder API](../mediastream_recording_api)) handles the recording `warning` event, allowing you to run code in response to non-fatal errors being thrown during media recording via a `MediaRecorder` (errors that don't halt recording).

## Syntax

    mediaRecorder.onwarning = function(event) { ... }
    mediaRecorder.addEventListener('warning', function(event) { ... })

## Example

    ...

      mediaRecorder.onwarning = function(e) {
        console.log("A warning has been raised: " + e.message);
      }

    ...

## Properties

`message`  
Contains information about the error that occurred.

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

`onwarning`

49

79

25-71

No

36

No

49

49

25

36

No

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onwarning" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onwarning</a>
