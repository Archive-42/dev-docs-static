OscillatorNode.detune
=====================

The `detune` property of the [`OscillatorNode`](../oscillatornode) interface is an [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam) representing detuning of oscillation in [cents](https://en.wikipedia.org/wiki/Cent_%28music%29).

Syntax
------

    var oscillator = audioCtx.createOscillator();
    oscillator.detune.setValueAtTime(100, audioCtx.currentTime); // value in cents

**Note:** though the `AudioParam` returned is read-only, the value it represents is not.

### Value

An [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam).

Example
-------

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an oscillator node. For applied examples/information, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.setValueAtTime(440, audioCtx.currentTime); // value in hertz
    oscillator.detune.setValueAtTime(100, audioCtx.currentTime); // value in cents
    oscillator.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-oscillatornode-detune">Web Audio API<br />
<span class="small">The definition of 'detune' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`detune`

20

12

25

No

15

6

≤37

25

25

14

6

1.5

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/detune" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/detune</a>
