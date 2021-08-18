OfflineAudioContext.OfflineAudioContext()
=========================================

The `OfflineAudioContext()` constructor—part of the [Web Audio API](../web_audio_api)—creates and returns a new [`OfflineAudioContext`](../offlineaudiocontext) object instance, which can then be used to render audio to an [`AudioBuffer`](../audiobuffer) rather than to an audio output device.

Syntax
------

    var offlineAudioCtx = new OfflineAudioContext(numberOfChannels, length, sampleRate);

    var offlineAudioCtx = new OfflineAudioContext(options);

### Parameters

You can specify the parameters for the `OfflineAudioContext()` constructor as either the same set of parameters as are inputs into the [`BaseAudioContext.createBuffer`](../baseaudiocontext/createbuffer) method, or by passing those parameters in an `options` object. Either way, the individual parameters are the same.

`numberOfChannels`  
An integer specifying the number of channels the resulting [`AudioBuffer`](../audiobuffer) should have.

`length`  
An integer specifying the size of the buffer to create for the audio context, in sample-frames, where one sample-frame is a unit that can contain a single sample of audio data for every channel in the audio data. For example, a 5-second buffer with a `sampleRate` of 48000Hz would have a length of `5 * 48000 = 240000` sample-frames.

`sampleRate`  
The sample-rate of the linear audio data in sample-frames per second. All user agents are required to support a range of 22050Hz to 96000Hz, and may support a wider range than that. The most commonly-used rate is 44100Hz, which is the sample rate used by CD audio.

It is important to note that, whereas you can create a new [`AudioContext`](../audiocontext) using the [`new AudioContext()`](../audiocontext/audiocontext) constructor with no arguments, the `OfflineAudioContext()` constructor requires three arguments, since it needs to create an `AudioBuffer`. This works in exactly the same way as when you create a new [`AudioBuffer`](../audiobuffer) with the [`BaseAudioContext.createBuffer`](../baseaudiocontext/createbuffer) method. For more detail, read [Audio buffers: frames, samples and channels](../web_audio_api/basic_concepts_behind_web_audio_api#audio_buffers.3a_frames.2c_samples_and_channels) from our [Basic concepts](../web_audio_api/basic_concepts_behind_web_audio_api) guide.

### Return value

A new [`OfflineAudioContext`](../offlineaudiocontext) object whose associated `AudioBuffer` is configured as requested.

Like a regular `AudioContext`, an `OfflineAudioContext` can be the target of events, therefore it implements the [`EventTarget`](../eventtarget) interface.

Example
-------

    const offlineCtx = new OfflineAudioContext({
      numberOfChannels: 2,
      length: 44100 * 40,
      sampleRate: 44100,
    });
    const source = offlineCtx.createBufferSource();
    // etc...

For a full working example, see our [offline-audio-context-promise](https://mdn.github.io/webaudio-examples/offline-audio-context-promise/) Github repo (see the [source code](https://github.com/mdn/webaudio-examples/blob/master/offline-audio-context-promise/index.html) too.)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocontext-offlineaudiocontext">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioContext()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`OfflineAudioContext`

35

25-57

≤79

53

No

22

15-44

14.1

6-14.1

4.4.3

≤37-57

35

25-57

53

22

14-43

14.5

6-14.5

3.0

1.5-7.0

`Parameters_accepted_in_an_object`

62

≤79

57

No

49

14.1

62

62

57

46

14.5

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/OfflineAudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/OfflineAudioContext</a>
