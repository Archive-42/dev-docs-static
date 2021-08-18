# AudioBuffer()

The `AudioBuffer` constructor of the [Web Audio API](../web_audio_api) creates a new [`AudioBuffer`](../audiobuffer) object.

## Syntax

    var audioBuffer = new AudioBuffer(options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

`options`  
Options are as follows:

- `length`: The size of the audio buffer in sample-frames. To determine the `length` to use for a specific number of seconds of audio, use `numSeconds * sampleRate`.
- `numberOfChannels`: The number of channels for the buffer. The default is 1, and all user agents are required to support at least 32 channels.
- `sampleRate`: The sample rate in Hz for the buffer. The default is the sample rate of the `context` used in constructing this object. User agents are required to support sample rates from 8,000 Hz to 96,000 Hz (but are allowed to go farther outside this range).

#### Deprecated parameters

`context` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A reference to an [`AudioContext`](../audiocontext). This parameter was removed from the spec.

### Return value

A new [`AudioBuffer`](../audiobuffer) object instance.

### Exceptions

`NotSupportedError`  
One or more of the options are negative or otherwise has an invalid value (such as `numberOfChannels` being higher than supported, or a `sampleRate` outside the nominal range).

`RangeError`  
There isn't enough memory available to allocate the buffer.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioBuffer">Web Audio API<br />
<span class="small">The definition of 'AudioBuffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioBuffer`

55

The `context` parameter was supported up until version 57, but has now been removed.

79

53

No

42

The `context` parameter was supported up until version 44, but has now been removed.

14.1

55

The `context` parameter was supported up until version 57, but has now been removed.

55

The `context` parameter was supported up until version 57, but has now been removed.

53

42

The `context` parameter was supported up until version 44, but has now been removed.

14.5

6.0

The `context` parameter was supported up until Samsung Internet 7.0, but has now been removed.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/AudioBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/AudioBuffer</a>
