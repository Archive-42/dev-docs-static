# DynamicsCompressorNode.ratio

The `ratio` property of the [`DynamicsCompressorNode`](../dynamicscompressornode) interface Is a [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) representing the amount of change, in dB, needed in the input for a 1 dB change in the output.

The `ratio` property's default value is `12` and it can be set between `1` and `20`.

<img src="data:image/png;base64,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" alt="Describes the effect of different ratio on the output signal" width="292" height="284" />

## Syntax

    var audioCtx = new AudioContext();
    var compressor = audioCtx.createDynamicsCompressor();
    compressor.ratio.value = 12;

### Value

An [`AudioParam`](../audioparam).

**Note**: Though the [`AudioParam`](../audioparam) returned is read-only, the value it represents is not.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-dynamicscompressornode-ratio">Web Audio API<br />
<span class="small">The definition of 'ratio' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ratio`

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

Yes

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/ratio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/ratio</a>
