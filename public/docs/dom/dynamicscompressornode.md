# DynamicsCompressorNode

The `DynamicsCompressorNode` interface provides a compression effect, which lowers the volume of the loudest parts of the signal in order to help prevent clipping and distortion that can occur when multiple sounds are played and multiplexed together at once. This is often used in musical production and game audio. `DynamicsCompressorNode` is an [`AudioNode`](audionode) that has exactly one input and one output; it is created using the [`BaseAudioContext.createDynamicsCompressor`](baseaudiocontext/createdynamicscompressor) method.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`DynamicsCompressorNode()`](dynamicscompressornode/dynamicscompressornode)  
Creates a new instance of an `DynamicsCompressorNode` object.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

[`DynamicsCompressorNode.threshold`](dynamicscompressornode/threshold) <span class="badge inline readonly">Read only </span>  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) representing the decibel value above which the compression will start taking effect.

[`DynamicsCompressorNode.knee`](dynamicscompressornode/knee) <span class="badge inline readonly">Read only </span>  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) containing a decibel value representing the range above the threshold where the curve smoothly transitions to the compressed portion.

[`DynamicsCompressorNode.ratio`](dynamicscompressornode/ratio) <span class="badge inline readonly">Read only </span>  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) representing the amount of change, in dB, needed in the input for a 1 dB change in the output.

[`DynamicsCompressorNode.reduction`](dynamicscompressornode/reduction) <span class="badge inline readonly">Read only </span>  
Is a `float` representing the amount of gain reduction currently applied by the compressor to the signal.

[`DynamicsCompressorNode.attack`](dynamicscompressornode/attack) <span class="badge inline readonly">Read only </span>  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) representing the amount of time, in seconds, required to reduce the gain by 10 dB.

[`DynamicsCompressorNode.release`](dynamicscompressornode/release) <span class="badge inline readonly">Read only </span>  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) representing the amount of time, in seconds, required to increase the gain by 10 dB.

## Methods

_No specific methods; inherits methods from its parent, [`AudioNode`](audionode)_.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dynamicscompressornode">Web Audio API<br />
<span class="small">The definition of 'DynamicsCompressorNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`DynamicsCompressorNode`

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

`DynamicsCompressorNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

`attack`

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

`reduction`

14

Before version 52, this was an `AudioParam.`.

12

25

No

15

6

≤37

Before version 52, this was an `AudioParam.`.

18

Before version 52, this was an `AudioParam.`.

25

14

Yes

1.0

Before Samsung Internet 6.0, this was an `AudioParam.`.

`release`

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

`threshold`

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode</a>
