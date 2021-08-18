WaveShaperNode.WaveShaperNode()
===============================

The `WaveShaperNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`WaveShaperNode`](../waveshapernode) object which is an [`AudioNode`](../audionode) that represents a non-linear distorter.

Syntax
------

    var waveShaperNode = new WaveShaperNode(context, options)

### Parameters

*Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary*.

*context*  
A reference to an [`AudioContext`](../audiocontext).

 *options* <span class="badge inline optional">Optional</span>   
Options are as follows:

-   `curve`: The shaping curve used for the waveshaping effect. The input signal is nominally within the range \[-1;1\].
-   `oversample`: Specifies what type of oversampling (if any) should be used when applying the shaping curve. Valid values are '`none`', '`2x`', or '`4x`'. The default is '`none`'.

### Return value

A new [`WaveShaperNode`](../waveshapernode) object instance.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-waveshapernode-waveshapernode">Web Audio API<br />
<span class="small">The definition of 'WaveShaperNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode/WaveShaperNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode/WaveShaperNode</a>
