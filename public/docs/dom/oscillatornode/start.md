# OscillatorNode.start()

The `start` method of the [`OscillatorNode`](../oscillatornode) interface specifies the exact time to start playing the tone. Its parameter is optional and default to `0`.

## Syntax

    oscillator.start(when); // start playing oscillator at the point in time specified by when

### Parameters

_when_ <span class="badge inline optional">Optional</span>  
An optional double representing the time (in seconds) when the oscillator should start, in the same coordinate system as [`AudioContext`](../audiocontext)'s `currentTime` attribute. If a value is not included or is less than `currentTime`, the oscillator starts playing immediately.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an oscillator node. For an applied example, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.setValueAtTime(3000, audioCtx.currentTime); // value in hertz
    oscillator.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-start">Web Audio API<br />
<span class="small">The definition of 'start' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.OscillatorNode.start`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/start</a>
