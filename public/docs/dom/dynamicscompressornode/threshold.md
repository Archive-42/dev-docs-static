DynamicsCompressorNode.threshold
================================

The `threshold` property of the [`DynamicsCompressorNode`](../dynamicscompressornode) interface is a [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) representing the decibel value above which the compression will start taking effect.

The `threshold` property's default value is `-24` and it can be set between `-100` and `0`.

<img src="data:image/png;base64,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" alt="The threshold attribute has no effect on signals lowers than its value, but induce volume reduction on signal stronger than its value." width="257" height="219" />

Syntax
------

    var audioCtx = new AudioContext();
    var compressor = audioCtx.createDynamicsCompressor();
    compressor.threshold.value = -50;

### Value

An [`AudioParam`](../audioparam).

**Note**: Though the [`AudioParam`](../audioparam) returned is read-only, the value it represents is not.

Example
-------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-dynamicscompressornode-threshold">Web Audio API<br />
<span class="small">The definition of 'threshold' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/threshold" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/threshold</a>
