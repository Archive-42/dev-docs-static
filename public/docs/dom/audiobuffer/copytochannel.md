# AudioBuffer.copyToChannel()

The `copyToChannel()` method of the [`AudioBuffer`](../audiobuffer) interface copies the samples to the specified channel of the `AudioBuffer`, from the source array.

## Syntax

    myArrayBuffer.copyToChannel(source, channelNumber, startInChannel);

### Parameters

source  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) that the channel data will be copied from.

channelNumber  
The channel number of the current [`AudioBuffer`](../audiobuffer) to copy the channel data to. If _channelNumber_ is greater than or equal to [`AudioBuffer.numberOfChannels`](numberofchannels), an `INDEX_SIZE_ERR` will be thrown.

startInChannel <span class="badge inline optional">Optional</span>  
An optional offset to copy the data to. If _startInChannel_ is greater than [`AudioBuffer.length`](length), an `INDEX_SIZE_ERR` will be thrown.

## Example

    var myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);
    var anotherArray = new Float32Array;
    // Copy channel data from second channel of myArrayBuffer.
    myArrayBuffer.copyFromChannel(anotherArray,1,0);
    // Copy data from anotherArray to first channel of myArrayBuffer. Both channels have the same data now.
    myArrayBuffer.copyToChannel (anotherArray,0,0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffer-copytochannel">Web Audio API<br />
<span class="small">The definition of 'copyToChannel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`copyToChannel`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/copyToChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/copyToChannel</a>
