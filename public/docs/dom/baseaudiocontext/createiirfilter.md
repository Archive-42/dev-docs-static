# BaseAudioContext.createIIRFilter()

The `createIIRFilter()` method of the [`BaseAudioContext`](../baseaudiocontext) interface creates an [`IIRFilterNode`](../iirfilternode), which represents a general **[infinite impulse response](#)** (IIR) filter which can be configured to serve as various types of filter.

## Syntax

    var iirFilter = AudioContext.createIIRFilter(feedforward, feedback);

### Parameters

`feedforward`  
An array of floating-point values specifying the feedforward (numerator) coefficients for the transfer function of the IIR filter. The maximum length of this array is 20, and at least one value must be nonzero.

`feedback`  
An array of floating-point values specifying the feedback (denominator) coefficients for the transfer function of the IIR filter. This array may have up to 20 members, the first of which must not be zero.

### Return value

An [`IIRFilterNode`](../iirfilternode) implementing the filter with the specified feedback and feedforward coefficient arrays.

### Exceptions

`InvalidStateError`  
All of the `feedforward` coefficients are 0, and/or the first `feedback` coefficient is 0.

`NotSupportedError`  
One or both of the input arrays exceeds 20 members.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createiirfilter">Web Audio API<br />
<span class="small">The definition of 'createIIRFilter()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createIIRFilter`

49

14

50

No

Yes

14.1

49

49

50

Yes

14.5

5.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [`IIRFilterNode`](../iirfilternode)
- [`AudioNode`](../audionode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createIIRFilter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createIIRFilter</a>
