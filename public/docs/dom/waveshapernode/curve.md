WaveShaperNode.curve
====================

The `curve` property of the [`WaveShaperNode`](../waveshapernode) interface is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) of numbers describing the distortion to apply.

The mid-element of the array is applied to any signal value of `0`, the first one to signal values of `-1`, and the last to signal values of `1`; values lower than `-1` or greater than `1` are treated like `-1` or `1` respectively.

If necessary, intermediate values of the distortion curve are linearly interpolated.

**Note**: The array can be a `null` value: in that case, no distortion is applied to the input signal.

Syntax
------

    var audioCtx = new AudioContext();
    var distortion = audioCtx.createWaveShaper();
    distortion.curve = myCurveDataArray; // myCurveDataArray is a Float32Array

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array).

Example
-------

The following example shows basic usage of an AudioContext to create a wave shaper node. For applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) [demo](https://mdn.github.io/voice-change-o-matic/) ([see app.js](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js) for relevant code).

**Note**: Sigmoid functions are commonly used for distortion curves because of their natural properties. Their S-shape, for instance, helps create a smoother sounding result. We found the below distortion curve code on [Stack Overflow](https://stackoverflow.com/questions/22312841/waveshaper-node-in-webaudio-how-to-emulate-distortion).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var distortion = audioCtx.createWaveShaper();

      ...

    function makeDistortionCurve(amount) {
      var k = typeof amount === 'number' ? amount : 50,
        n_samples = 44100,
        curve = new Float32Array(n_samples),
        deg = Math.PI / 180,
        i = 0,
        x;
      for ( ; i < n_samples; ++i ) {
        x = i * 2 / n_samples - 1;
        curve[i] = ( 3 + k ) * x * 20 * deg / ( Math.PI + k * Math.abs(x) );
      }
      return curve;
    };

      ...

    distortion.curve = makeDistortionCurve(400);
    distortion.oversample = '4x';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-waveshapernode-curve">Web Audio API<br />
<span class="small">The definition of 'curve' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`curve`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode/curve" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode/curve</a>
