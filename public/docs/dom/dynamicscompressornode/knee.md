# DynamicsCompressorNode.knee

The `knee` property of the [`DynamicsCompressorNode`](../dynamicscompressornode) interface is a [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) containing a decibel value representing the range above the threshold where the curve smoothly transitions to the compressed portion.

The `knee` property's default value is `30` and it can be set between `0` and `40`.

<img src="data:image/png;base64,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" alt="Describes the effect of a knee, showing two curves one for a hard knee, the other for a soft knee." width="257" height="244" />

## Syntax

    var audioCtx = new AudioContext();
    var compressor = audioCtx.createDynamicsCompressor();
    compressor.knee.value = 40;

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-dynamicscompressornode-knee">Web Audio API<br />
<span class="small">The definition of 'knee' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`knee`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/knee" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/knee</a>
