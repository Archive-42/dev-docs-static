# MediaRecorder.resume()

The `MediaRecorder.resume()` method (part of the [MediaRecorder API](../mediastream_recording_api)) is used to resume media recording when it has been previously paused.

When the `resume()` method is invoked, the browser queues a task that runs the following steps:

1.  If [`MediaRecorder.state`](state) is "inactive", raise a DOM `InvalidState` error and terminate these steps. If [`MediaRecorder.state`](state) is not "inactive", continue to the next step.
2.  Set [`MediaRecorder.state`](state) to "recording".
3.  Continue gathering data into the current [`Blob`](../blob).
4.  Raise a `resume` event.

## Syntax

    MediaRecorder.resume()

### Errors

An `InvalidState` error is raised if the `resume()` method is called while the `MediaRecorder` object’s [`MediaRecorder.state`](state) is "inactive" — the recording cannot be resumed if it is not already paused; if [`MediaRecorder.state`](state) is already "recording", `resume()` has no effect.

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

    ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-resume">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.resume()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`resume`

49

79

25

No

36

14.1

49

49

25

36

14.5

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/resume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/resume</a>
