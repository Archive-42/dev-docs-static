GainNode
========

The `GainNode` interface represents a change in volume. It is an [`AudioNode`](audionode) audio-processing module that causes a given gain to be applied to the input data before its propagation to the output. A `GainNode` always has exactly one input and one output, both with the same number of channels.

The gain is a unitless value, changing with time, that is multiplied to each corresponding sample of all input channels. If modified, the new gain is instantly applied, causing unaesthetic 'clicks' in the resulting audio. To prevent this from happening, never change the value directly but use the exponential interpolation methods on the [`AudioParam`](audioparam) interface.

<img src="data:image/png;base64,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" alt="The GainNode is increasing the gain of the output." width="774" height="116" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Constructor
-----------

[`GainNode()`](gainnode/gainnode)  
Creates a new instance of a `GainNode` object. You shouldn't manually create a gain node; instead, use the method [`BaseAudioContext.createGain`](baseaudiocontext/creategain).

Properties
----------

*Inherits properties from its parent, [`AudioNode`](audionode)*.

 [`GainNode.gain`](gainnode/gain) <span class="badge inline readonly">Read only </span>   
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing the amount of gain to apply. You have to set [`AudioParam.value`](audioparam/value) or use the methods of `AudioParam` to change the effect of gain.

Methods
-------

*No specific method; inherits methods from its parent, [`AudioNode`](audionode)*.

Example
-------

The following example shows basic usage of an [`AudioContext`](audiocontext) to create a `GainNode`, which is then used to mute and unmute the audio when a Mute button is clicked by changing the `gain` property value.

The below snippet wouldn't work as is — for a complete working example, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo ([view source](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js).)

    <div>
      <button class="mute">Mute button</button>
    </div>

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var gainNode = audioCtx.createGain();
    var mute = document.querySelector('.mute');
    var source;

    if (navigator.mediaDevices.getUserMedia) {
     navigator.mediaDevices.getUserMedia (
       // constraints - only audio needed for this app
       {
         audio: true
       },

       // Success callback
       function(stream) {
         source = audioCtx.createMediaStreamSource(stream);

       },

       // Error callback
       function(err) {
         console.log('The following gUM error occurred: ' + err);
       }
      );
    } else {
       console.log('getUserMedia not supported on your browser!');
    }

    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

      ...

    mute.onclick = voiceMute;

    function voiceMute() {
      if(mute.id == "") {
        // 0 means mute. If you still hear something, make sure you haven't
        // connected your source into the output in addition to using the GainNode.
        gainNode.gain.setValueAtTime(0, audioCtx.currentTime);
        mute.id = "activated";
        mute.textContent = "Unmute";
      } else {
        gainNode.gain.setValueAtTime(1, audioCtx.currentTime);
        mute.id = "";
        mute.textContent = "Mute";
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#gainnode">Web Audio API<br />
<span class="small">The definition of 'GainNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`GainNode`

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

`GainNode`

55

Before Chrome 59, the default values were not supported.

79

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

`gain`

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

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GainNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GainNode</a>
