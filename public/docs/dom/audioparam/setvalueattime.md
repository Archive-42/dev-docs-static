# AudioParam.setValueAtTime()

The `setValueAtTime()` method of the [`AudioParam`](../audioparam) interface schedules an instant change to the `AudioParam` value at a precise time, as measured against [`AudioContext.currentTime`](../baseaudiocontext/currenttime). The new value is given in the value parameter.

## Syntax

    var AudioParam = AudioParam.setValueAtTime(value, startTime)

### Parameters

value  
A floating point number representing the value the AudioParam will change to at the given time.

startTime  
A double representing the time (in seconds) after the [`AudioContext`](../audiocontext) was first created that the change in value will happen. A [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) is thrown if this value is negative.

### Returns

A reference to this `AudioParam` object. In some browsers older implementations of this interface return void.

## Examples

This simple example features a media element source with two control buttons (see our [webaudio-examples repo](https://github.com/mdn/webaudio-examples/blob/master/audio-param/index.html) for the source code, or [view the example live](https://mdn.github.io/webaudio-examples/audio-param/)). When the buttons are pressed, the `currGain` variable is incremented/decremented by 0.25, then the `setValueAtTime()` method is used to set the gain value equal to `currGain`, one second from now (`audioCtx.currentTime + 1`.)

    // create audio context
    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    // set basic variables for example
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    var targetAtTimePlus = document.querySelector('.set-target-at-time-plus');
    var targetAtTimeMinus = document.querySelector('.set-target-at-time-minus');

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a gain node and set it's gain value to 0.5
    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.5;
    var currGain = gainNode.gain.value;

    // connect the AudioBufferSourceNode to the gainNode
    // and the gainNode to the destination
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    // set buttons to do something onclick
    targetAtTimePlus.onclick = function() {
      currGain += 0.25;
      gainNode.gain.setValueAtTime(currGain, audioCtx.currentTime + 1);
    }

    targetAtTimeMinus.onclick = function() {
      currGain -= 0.25;
      gainNode.gain.setValueAtTime(currGain, audioCtx.currentTime + 1);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-setvalueattime">Web Audio API<br />
<span class="small">The definition of 'setValueAtTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setValueAtTime`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setValueAtTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setValueAtTime</a>
