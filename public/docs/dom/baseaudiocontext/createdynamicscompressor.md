# BaseAudioContext.createDynamicsCompressor()

The `createDynamicsCompressor()` method of the [`BaseAudioContext`](../baseaudiocontext) Interface is used to create a [`DynamicsCompressorNode`](../dynamicscompressornode), which can be used to apply compression to an audio signal.

Compression lowers the volume of the loudest parts of the signal and raises the volume of the softest parts. Overall, a louder, richer, and fuller sound can be achieved. It is especially important in games and musical applications where large numbers of individual sounds are played simultaneously, where you want to control the overall signal level and help avoid clipping (distorting) of the audio output.

## Syntax

    baseAudioCtx.createDynamicsCompressor();

### Returns

A [`DynamicsCompressorNode`](../dynamicscompressornode).

## Example

The below code demonstrates a simple usage of `createDynamicsCompressor()` to add compression to an audio track. For a more complete example, have a look at our [basic Compressor example](https://mdn.github.io/webaudio-examples/compressor-example/) ([view the source code](https://github.com/mdn/webaudio-examples/tree/master/compressor-example)).

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a compressor node
    var compressor = audioCtx.createDynamicsCompressor();
    compressor.threshold.setValueAtTime(-50, audioCtx.currentTime);
    compressor.knee.setValueAtTime(40, audioCtx.currentTime);
    compressor.ratio.setValueAtTime(12, audioCtx.currentTime);
    compressor.attack.setValueAtTime(0, audioCtx.currentTime);
    compressor.release.setValueAtTime(0.25, audioCtx.currentTime);

    // connect the AudioBufferSourceNode to the destination
    source.connect(audioCtx.destination);

    button.onclick = function() {
      var active = button.getAttribute('data-active');
      if(active == 'false') {
        button.setAttribute('data-active', 'true');
        button.textContent = 'Remove compression';

        source.disconnect(audioCtx.destination);
        source.connect(compressor);
        compressor.connect(audioCtx.destination);
      } else if(active == 'true') {
        button.setAttribute('data-active', 'false');
        button.textContent = 'Add compression';

        source.disconnect(compressor);
        compressor.disconnect(audioCtx.destination);
        source.connect(audioCtx.destination);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createdynamicscompressor">Web Audio API<br />
<span class="small">The definition of 'createDynamicsCompressor()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createDynamicsCompressor`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createDynamicsCompressor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createDynamicsCompressor</a>
