# AudioBuffer.copyFromChannel()

The `copyFromChannel()` method of the [`AudioBuffer`](../audiobuffer) interface copies the audio sample data from the specified channel of the `AudioBuffer` to a specified [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array).

## Syntax

    myArrayBuffer.copyFromChannel(destination, channelNumber, startInChannel);

### Parameters

`destination`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) to copy the channel's samples to.

`channelNumber`  
The channel number of the current `AudioBuffer` to copy the channel data from.

`startInChannel` <span class="badge inline optional">Optional</span>  
An optional offset into the source channel's buffer from which to begin copying samples. If not specified, a value of 0 (the beginning of the buffer) is assumed by default.

### Return value

`undefined`.

### Exceptions

`indexSizeError`  
One of the input parameters has a value that is outside the accepted range:

- The value of `channelNumber` specifies a channel number which doesn't exist (that is, it's greater than or equal to the value of [`numberOfChannels`](numberofchannels) on the channel).
- The value of `startInChannel` is outside the current range of samples that already exist in the source buffer; that is, it's greater than its current [`length`](length).

## Example

This example creates a new audio buffer, then copies the samples from another channel into it.

    var myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);
    var anotherArray = new Float32Array(length);
    myArrayBuffer.copyFromChannel(anotherArray, 1, 0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffer-copyfromchannel">Web Audio API<br />
<span class="small">The definition of 'copyFromChannel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`copyFromChannel`

43

13

25

No

30

14.1

43

43

25

30

14.5

4.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/copyFromChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/copyFromChannel</a>
