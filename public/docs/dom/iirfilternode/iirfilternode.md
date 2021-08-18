IIRFilterNode()
===============

The `IIRFilterNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`IIRFilterNode`](../iirfilternode) object which an [`AudioNode`](../audionode) processor which implements a general infinite impulse response filter.

Syntax
------

    var iIRFilterNode = new IIRFilterNode(context, options)

### Parameters

*Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary*.

*context*  
A reference to an [`AudioContext`](../audiocontext).

*options*  
Options are as follows:

-   `feedforward`: A sequence of feedforward coefficients.
-   `feedback`: A sequence of feedback coefficients.

Unlike other nodes in the Web Audio API, the options passed into the IIR filter upon creation are not optional. The filter needs these values to work and with the vast range of filters available, there is no default.

### Return value

A new [`IIRFilterNode`](../iirfilternode) object instance.

Examples
--------

    let feedForward = [0.00020298, 0.0004059599, 0.00020298];
    let feedBackward = [1.0126964558, -1.9991880801, 0.9873035442];

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();

    const iirFilter = new IIRFilterNode(audioCtx, { feedforward: feedForward, feedback: feedBackward });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-iirfilternode-iirfilternode">Web Audio API<br />
<span class="small">The definition of 'IIRFilterNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`IIRFilterNode`

55

Before version 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before version 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode/IIRFilterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode/IIRFilterNode</a>
