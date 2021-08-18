StereoPannerNode.pan
====================

The `pan` property of the [`StereoPannerNode`](../stereopannernode) interface is an [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam) representing the amount of panning to apply. The value can range between `-1` (full left pan) and `1` (full right pan).

Syntax
------

    var audioCtx = new AudioContext();
    var panNode = audioCtx.createStereoPanner();
    panNode.pan.value = -0.5;

### Returned value

An [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam) containing the panning to apply.

**Note**: Though the `AudioParam` returned is read-only, the value it represents is not.

Example
-------

In our [StereoPannerNode example](https://mdn.github.io/webaudio-examples/stereo-panner-node/) ([see source code](https://github.com/mdn/webaudio-examples/tree/master/stereo-panner-node)) HTML we have a simple [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element along with a slider [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) to increase and decrease pan value. In the JavaScript we create a [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) and a [`StereoPannerNode`](../stereopannernode), and connect the two together using the `connect() `method. We then use an `oninput` event handler to change the value of the [`StereoPannerNode.pan`](pan) parameter and update the pan value display when the slider is moved.

Moving the slider left and right while the music is playing pans the music across to the left and right speakers of the output, respectively.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var myAudio = document.querySelector('audio');

    var panControl = document.querySelector('.panning-control');
    var panValue = document.querySelector('.panning-value');

    pre.innerHTML = myScript.innerHTML;

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a stereo panner
    var panNode = audioCtx.createStereoPanner();

    // Event handler function to increase panning to the right and left
    // when the slider is moved

    panControl.oninput = function() {
      panNode.pan.setValueAtTime(panControl.value, audioCtx.currentTime);
      panValue.innerHTML = panControl.value;
    }

    // connect the MediaElementAudioSourceNode to the panNode
    // and the panNode to the destination, so we can play the
    // music and adjust the panning using the controls
    source.connect(panNode);
    panNode.connect(audioCtx.destination);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-stereopannernode-pan">Web Audio API<br />
<span class="small">The definition of 'pan' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`pan`

41

12

37

No

28

14.1

41

41

37

28

14.5

4.0

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode/pan" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode/pan</a>
