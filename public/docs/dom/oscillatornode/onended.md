# OscillatorNode.onended

The `onended` property of the [`OscillatorNode`](../oscillatornode) interface is used to set the event handler for the ended event, which fires when the tone has stopped playing.

## Syntax

    var oscillator = audioCtx.createOscillator();
    oscillator.onended = function() { ... };

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an oscillator node. For an applied example, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.value = 440; // value in hertz
    oscillator.start(); // start the tone playing

    oscillator.stop(5); // the tone will stop again in 5 seconds.

    oscillator.onended = function() {
      console.log('Your tone has now stopped playing!');
    }

## Properties

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-onended">Web Audio API<br />
<span class="small">The definition of 'onended' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.OscillatorNode.onended`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/onended" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/onended</a>
