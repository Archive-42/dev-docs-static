# IIRFilterNode

The `IIRFilterNode` interface of the [Web Audio API](web_audio_api) is a [`AudioNode`](audionode) processor which implements a general **[infinite impulse response](https://en.wikipedia.org/wiki/Infinite_impulse_response)** (IIR) filter; this type of filter can be used to implement tone control devices and graphic equalizers as well. It lets the parameters of the filter response be specified, so that it can be tuned as needed.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td>Same as on the input</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Typically, it's best to use the [`BiquadFilterNode`](biquadfilternode) interface to implement higher-order filters. There are several reasons why:

- Biquad filters are typically less sensitive to numeric quirks.
- The filter parameters of biquad filters can be automated.
- All even-ordered IIR filters can be created using [`BiquadFilterNode`](biquadfilternode).

However, if you need to create an odd-ordered IIR filter, you'll need to use `IIRFilterNode`. You may also find this interface useful if you don't need automation, or for other reasons.

Once the node has been created, you can't change its coefficients.

`IIRFilterNode`s have a tail-time reference; they continue to output non-silent audio with zero input. As an IIR filter, the non-zero input continues forever, but this can be limited after some finite time in practice, when the output has approached zero closely enough. The actual time that takes depends on the filter coefficients provided.

## Constructor

[`IIRFilterNode()`](iirfilternode/iirfilternode)  
Creates a new instance of an IIRFilterNode object.

## Properties

_This interface has no properties of its own; however, it inherits properties from its parent, [`AudioNode`](audionode)_.

## Methods

_Inherits methods from its parent, [`AudioNode`](audionode). It also has the following additional methods:_

[`getFrequencyResponse()`](iirfilternode/getfrequencyresponse)  
Uses the filter's current parameter settings to calculate the response for frequencies specified in the provided array of frequencies.

## Examples

You can find a simple IIR filter demo live [on Codepen](https://codepen.io/Rumyra/pen/oPxvYB/). Also see the [source code on GitHub](https://github.com/mdn/webaudio-examples/tree/master/iirfilter-node). It includes some different coefficient values for different lowpass frequencies — you can change the value of the <span class="pl-s1">`filterNumber` constant to a value between 0 and 3 to check out the different available effects.</span>

<span class="pl-s1">Also see our [Using IIR filters](web_audio_api/using_iir_filters) guide for a full explanation.</span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#iirfilternode">Web Audio API<br />
<span class="small">The definition of 'IIRFilterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial Definition</td></tr></tbody></table>

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

`IIRFilterNode`

49

≤18

50

No

36

14.1

49

49

50

36

14.5

5.0

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

`getFrequencyResponse`

49

14

50

No

36

14.1

49

49

50

36

14.5

5.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [`AudioNode`](audionode)
- [`BiquadFilterNode`](biquadfilternode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode</a>
