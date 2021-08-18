# AudioContext.suspend()

The `suspend()` method of the [`AudioContext`](../audiocontext) Interface suspends the progression of time in the audio context, temporarily halting audio hardware access and reducing CPU/battery usage in the process — this is useful if you want an application to power down the audio hardware when it will not be using an audio context for a while.

This method will cause an `INVALID_STATE_ERR` exception to be thrown if called on an [`OfflineAudioContext`](../offlineaudiocontext).

## Syntax

    var audioCtx = new AudioContext();
    audioCtx.suspend().then(function() { ... });

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with void. The promise is rejected if the context has already been closed.

## Example

The following snippet is taken from our [AudioContext states demo](https://github.com/mdn/webaudio-examples/blob/master/audiocontext-states/index.html) ([see it running live](https://mdn.github.io/webaudio-examples/audiocontext-states/).) When the suspend/resume button is clicked, the [`AudioContext.state`](../baseaudiocontext/state) is queried — if it is `running`, `suspend()` is called; if it is `suspended`, [`resume()`](resume) is called. In each case, the text label of the button is updated as appropriate once the promise resolves.

    susresBtn.onclick = function() {
      if(audioCtx.state === 'running') {
        audioCtx.suspend().then(function() {
          susresBtn.textContent = 'Resume context';
        });
      } else if(audioCtx.state === 'suspended') {
        audioCtx.resume().then(function() {
          susresBtn.textContent = 'Suspend context';
        });
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-suspend">Web Audio API<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`suspend`

43

14

40

No

Yes

9

43

43

40

Yes

9

4.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/suspend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/suspend</a>
