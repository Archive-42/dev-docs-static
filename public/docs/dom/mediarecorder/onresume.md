# MediaRecorder.onresume

The `MediaRecorder.onresume `event handler (part of the [MediaRecorder API](../mediastream_recording_api)) handles the `resume` event, allowing you to run code in response to the media recording being resumed after pausing.

The `resume` event is thrown as a result of the [`MediaRecorder.resume()`](resume) method being invoked.

## Syntax

    MediaRecorder.onresume = function(event) { ... }
    MediaRecorder.addEventListener('resume', function(event) { ... })

## Example

    ...

      pause.onclick = function() {
        if(MediaRecorder.state === "recording") {
          mediaRecorder.pause();
          // recording paused
        } else if(MediaRecorder.state === "paused") {
          mediaRecorder.resume();
          // resume recording
        }
      }

      mediaRecorder.onpause = function() {
        // do something in response to
        // recording being paused
      }

      mediaRecorder.onresume = function() {
        // do something in response to
        // recording being resumed
      }

    ...

## Properties

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-onresume">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.onresume' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onresume`

49

79

65

No

36

14.1

49

49

65

36

14.5

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onresume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onresume</a>
