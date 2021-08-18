# OscillatorNode.OscillatorNode()

The `OscillatorNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`OscillatorNode`](../oscillatornode) object which is an [`AudioNode`](../audionode) that represents a periodic waveform, like a sine wave, optionally setting the node's properties' values to match values in a specified object.

If the default values of the properties are acceptable, you can optionally use the [`BaseAudioContext.createOscillator`](../baseaudiocontext/createoscillator) factory method instead.

## Syntax

    var oscillatorNode = new OscillatorNode(context, options)

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

`context`  
A reference to an [`AudioContext`](../audiocontext).

`options` <span class="badge inline optional">Optional</span>  
An object whose properties specify the initial values for the oscillator node's properties. Any properties omitted from the object will take on the default value as documented.

`type`  
The shape of the wave produced by the node. Valid values are '`sine`', '`square`', '`sawtooth`', '`triangle`' and '`custom`'. The default is '`sine`'.

`detune`  
A detuning value (in cents) which will offset the `frequency` by the given amount. Its default is 0.

`frequency`  
The frequency (in [hertz](https://en.wikipedia.org/wiki/Hertz)) of the periodic waveform. Its default is 440.

`periodicWave`  
An arbitrary period waveform described by a [`PeriodicWave`](../periodicwave) object.

### Return value

A new [`OscillatorNode`](../oscillatornode) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-oscillatornode-oscillatornode">Web Audio API<br />
<span class="small">The definition of 'OscillatorNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/OscillatorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/OscillatorNode</a>
