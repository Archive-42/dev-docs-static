StereoPannerNode
================

The `StereoPannerNode` interface of the [Web Audio API](web_audio_api) represents a simple stereo panner node that can be used to pan an audio stream left or right. It is an [`AudioNode`](audionode) audio-processing module that positions an incoming audio stream in a stereo image using a low-cost equal-power [panning algorithm](https://webaudio.github.io/web-audio-api/#panning-algorithm).

The [`pan`](stereopannernode/pan) property takes a unitless value between `-1` (full left pan) and `1` (full right pan). This interface was introduced as a much simpler way to apply a simple panning effect than having to use a full [`PannerNode`](pannernode).

<img src="data:image/png;base64,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" width="687" height="89" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Constructor
-----------

[`StereoPannerNode()`](stereopannernode/stereopannernode)  
Creates a new instance of a `StereoPannerNode` object.

Properties
----------

*Inherits properties from its parent, [`AudioNode`](audionode)*.

 [`StereoPannerNode.pan`](stereopannernode/pan) <span class="badge inline readonly">Read only </span>   
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing the amount of panning to apply.

Methods
-------

*No specific method; inherits methods from its parent, [`AudioNode`](audionode)*.

Example
-------

In our [StereoPannerNode example](https://mdn.github.io/webaudio-examples/stereo-panner-node/) ([see source code](https://github.com/mdn/webaudio-examples/tree/master/stereo-panner-node)) HTML we have a simple [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element along with a slider [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) to increase and decrease pan value. In the JavaScript we create a [`MediaElementAudioSourceNode`](mediaelementaudiosourcenode) and a [`StereoPannerNode`](stereopannernode), and connect the two together using the `connect() `method. We then use an `oninput` event handler to change the value of the [`StereoPannerNode.pan`](stereopannernode/pan) parameter and update the pan value display when the slider is moved.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#stereopannernode">Web Audio API<br />
<span class="small">The definition of 'StereoPannerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`StereoPannerNode`

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

`StereoPannerNode`

55

Before Chrome 59, the default values were not supported.

≤79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

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

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode</a>
