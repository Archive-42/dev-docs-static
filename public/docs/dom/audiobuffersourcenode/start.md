# AudioBufferSourceNode.start()

The `start()` method of the [`AudioBufferSourceNode`](../audiobuffersourcenode) Interface is used to schedule playback of the audio data contained in the buffer, or to begin playback immediately.

## Syntax

    AudioBufferSourceNode.start([when][, offset][, duration]);

### Parameters

`when` <span class="badge inline optional">Optional</span>  
The time, in seconds, at which the sound should begin to play, in the same time coordinate system used by the [`AudioContext`](../audiocontext). If `when` is less than ([`AudioContext.currentTime`](../baseaudiocontext/currenttime), or if it's 0, the sound begins to play at once. **The default value is 0.**

`offset` <span class="badge inline optional">Optional</span>  
An offset, specified as the number of seconds in the same time coordinate system as the `AudioContext`, to the time within the audio buffer that playback should begin. For example, to start playback halfway through a 10-second audio clip, `offset` should be 5. The default value, 0, will begin playback at the beginning of the audio buffer, and offsets past the end of the audio which will be played (based on the audio buffer's [`duration`](../audiobuffer/duration) and/or the [`loopEnd`](loopend) property) are silently clamped to the maximum value allowed. The computation of the offset into the sound is performed using the sound buffer's natural sample rate, rather than the current playback rate, so even if the sound is playing at twice its normal speed, the midway point through a 10-second audio buffer is still 5.

`duration` <span class="badge inline optional">Optional</span>  
The duration of the sound to be played, specified in seconds. If this parameter isn't specified, the sound plays until it reaches its natural conclusion or is stopped using the [`stop()`](../audioscheduledsourcenode/stop) method. Using this parameter is functionally identical to calling `start(when, offset)` and then calling `stop(when+duration)`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`TypeError`  
A negative value was specified for one or more of the three time parameters. Please don't attempt to tamper with the laws of temporal physics.

`InvalidStateError`  
`start()` has already been called. You can only call this function once during the lifetime of an `AudioBufferSourceNode`.

## Examples

The most simple example just starts the audio buffer playing from the beginning — you don't need to specify any parameters in this case:

    source.start();

The following more complex example will, 1 second from now, start playing 10 seconds worth of sound starting 3 seconds into the audio buffer.

    source.start(audioCtx.currentTime + 1,3,10);

For a more complete example showing `start()` in use, check out our [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata) example. You can also [run the code example live](https://mdn.github.io/webaudio-examples/decode-audio-data/), or [view the source](https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-start">Web Audio API<br />
<span class="small">The definition of 'start()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`start`

24

12

25

No

15

6.1

≤37

25

25

14

7

1.5

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/start</a>
