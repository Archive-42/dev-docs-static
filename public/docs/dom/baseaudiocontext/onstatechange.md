# BaseAudioContext.onstatechange

The `onstatechange` property of the [`BaseAudioContext`](../baseaudiocontext) interface defines an event handler function to be called when the `statechange` event fires: this occurs when the audio context's state changes.

## Syntax

    baseAudioContext.onstatechange = function() { ... };

## Example

The following snippet is taken from our [AudioContext states demo](https://github.com/mdn/webaudio-examples) ([see it running live](https://mdn.github.io/webaudio-examples/audiocontext-states/).) The `onstatechange` handler is used to log the current [`state`](state) to the console every time it changes.

    audioCtx.onstatechange = function() {
      console.log(audioCtx.state);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-onstatechange">Web Audio API<br />
<span class="small">The definition of 'onstatechange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onstatechange`

43

14

40

No

Yes

9

Yes

Yes

40

Yes

9

Yes

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/onstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/onstatechange</a>
