# OscillatorNode.stop()

The `stop` method of the [`OscillatorNode`](../oscillatornode) interface specifies the time to stop playing the tone. Its parameter is optional and defaults to `0`.

## Syntax

    oscillator.stop(when); // stop playing oscillator at when

### Parameters

_when_ <span class="badge inline optional">Optional</span>  
An optional double representing the [audio context time](../baseaudiocontext/currenttime) when the oscillator should stop. If a value is not included, it defaults to `0`. If the time is equal to or before the current audio context time, the oscillator will stop playing immediately.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an oscillator node. For an applied example, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();
    oscillator.connect(audioCtx.destination);

    oscillator.start();

    oscillator.stop(audioCtx.currentTime + 2); // stop 2 seconds after the current time

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-stop">Web Audio API<br />
<span class="small">The definition of 'stop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.OscillatorNode.stop`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/stop</a>
