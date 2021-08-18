GainNode.gain
=============

The `gain` property of the [`GainNode`](../gainnode) interface is an [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam) representing the amount of gain to apply.

Syntax
------

    var audioCtx = new AudioContext();
    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.5;

### Value

An [`AudioParam`](../audioparam).

**Note**: Though the `AudioParam` returned is read-only, the value it represents is not.

Example
-------

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create a `GainNode`, which is then used to mute and unmute the audio when a Mute button is clicked by changing the `gain` property value.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-gainnode-gain">Web Audio API<br />
<span class="small">The definition of 'gain' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GainNode/gain" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GainNode/gain</a>
