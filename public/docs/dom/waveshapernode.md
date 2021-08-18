WaveShaperNode
==============

The `WaveShaperNode` interface represents a non-linear distorter. It is an [`AudioNode`](audionode) that uses a curve to apply a wave shaping distortion to the signal. Beside obvious distortion effects, it is often used to add a warm feeling to the signal.

A `WaveShaperNode` always has exactly one input and one output.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Constructor
-----------

[`WaveShaperNode()`](waveshapernode/waveshapernode)  
Creates a new instance of an `WaveShaperNode` object.

Properties
----------

*Inherits properties from its parent, [`AudioNode`](audionode)*.

[`WaveShaperNode.curve`](waveshapernode/curve)  
Is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) of numbers describing the distortion to apply.

[`WaveShaperNode.oversample`](waveshapernode/oversample)  
Is an enumerated value indicating if oversampling must be used. Oversampling is a technique for creating more samples (up-sampling) before applying the distortion effect to the audio signal.

Methods
-------

*No specific method; inherits methods from its parent, [`AudioNode`](audionode)*.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#waveshapernode">Web Audio API<br />
<span class="small">The definition of 'WaveShaperNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`WaveShaperNode`

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

`WaveShaperNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

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

`oversample`

14

12

26

No

15

6

≤37

18

26

14

Yes

1.0

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode</a>
