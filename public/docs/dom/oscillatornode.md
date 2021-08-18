OscillatorNode
==============

The `OscillatorNode` interface represents a periodic waveform, such as a sine wave. It is an [`AudioScheduledSourceNode`](audioscheduledsourcenode) audio-processing module that causes a specified frequency of a given wave to be created—in effect, a constant tone.

An `OscillatorNode` is created using the [`BaseAudioContext.createOscillator()`](baseaudiocontext/createoscillator) method. It always has exactly one output and no inputs. Its basic property defaults (see [`AudioNode`](audionode) for definitions) are:

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>max</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>speakers</code></td></tr></tbody></table>

Constructor
-----------

[`OscillatorNode()`](oscillatornode/oscillatornode)  
Creates a new instance of an `OscillatorNode` object, optionally providing an object specifying default values for the node's [properties](#properties). If the default values are acceptable, you can call the [`BaseAudioContext.createOscillator()`](baseaudiocontext/createoscillator) factory method.

Properties
----------

*Inherits properties from its parent, [`AudioScheduledSourceNode`](audioscheduledsourcenode), and adds the following properties:*

[`OscillatorNode.frequency`](oscillatornode/frequency)  
An [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing the frequency of oscillation in hertz (though the `AudioParam` returned is read-only, the value it represents is not). The default value is 440 Hz (a standard middle-A note).

[`OscillatorNode.detune`](oscillatornode/detune)  
An [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing detuning of oscillation in cents (though the `AudioParam` returned is read-only, the value it represents is not). The default value is 0.

[`OscillatorNode.type`](oscillatornode/type)  
A string which specifies the shape of waveform to play; this can be one of a number of standard values, or `custom` to use a [`PeriodicWave`](periodicwave) to describe a custom waveform. Different waves will produce different tones. Standard values are `"sine"`, `"square"`, `"sawtooth"`, `"triangle"` and `"custom"`. The default is `"sine"`.

### Event handlers

[`OscillatorNode.onended`](oscillatornode/onended)  
Sets the event handler for the `ended` event, which fires when the tone has stopped playing.

Methods
-------

*Inherits methods from its parent, [`AudioScheduledSourceNode`](audioscheduledsourcenode), and adds the following:*

[`OscillatorNode.setPeriodicWave()`](oscillatornode/setperiodicwave)  
Sets a [`PeriodicWave`](periodicwave) which describes a periodic waveform to be used instead of one of the standard waveforms; calling this sets the `type` to `custom`.

[`OscillatorNode.start()`](oscillatornode/start)  
Specifies the exact time to start playing the tone.

[`OscillatorNode.stop()`](oscillatornode/stop)  
Specifies the time to stop playing the tone.

Examples
--------

The following example shows basic usage of an [`AudioContext`](audiocontext) to create an oscillator node and to start playing a tone on it. For an applied example, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    const oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.setValueAtTime(440, audioCtx.currentTime); // value in hertz
    oscillator.connect(audioCtx.destination);
    oscillator.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#oscillatornode">Web Audio API<br />
<span class="small">The definition of 'OscillatorNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`OscillatorNode`

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

`OscillatorNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

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

`frequency`

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

`setPeriodicWave`

30

12

25

No

17

8

≤37

30

25

18

8

2.0

`type`

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

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode</a>
