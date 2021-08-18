# AudioContext.close()

The `close()` method of the [`AudioContext`](../audiocontext) Interface closes the audio context, releasing any system audio resources that it uses.

Closed contexts cannot have new nodes created, but can decode audio data, create buffers, etc.

This function does not automatically release all `AudioContext`-created objects, unless other references have been released as well; however, it will forcibly release any system audio resources that might prevent additional `AudioContexts` from being created and used, suspend the progression of audio time in the audio context, and stop processing audio data. The returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves when all `AudioContext`-creation-blocking resources have been released. This method throws an `INVALID_STATE_ERR` exception if called on an [`OfflineAudioContext`](../offlineaudiocontext).

## Syntax

    var audioCtx = new AudioContext();
    audioCtx.close().then(function() { ... });
    await audioCtx.close();

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with void.

## Example

The following snippet is taken from our [AudioContext states demo](https://github.com/mdn/webaudio-examples/blob/master/audiocontext-states/index.html) ([see it running live](https://mdn.github.io/webaudio-examples/audiocontext-states/).) When the stop button is clicked, `close()` is called. When the promise resolves, the example is reset to its beginning state.

    stopBtn.onclick = function() {
      audioCtx.close().then(function() {
        startBtn.removeAttribute('disabled');
        susresBtn.setAttribute('disabled', 'disabled');
        stopBtn.setAttribute('disabled', 'disabled');
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-close">Web Audio API<br />
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

`close`

42

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/close</a>
