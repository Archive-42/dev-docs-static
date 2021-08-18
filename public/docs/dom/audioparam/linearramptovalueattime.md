# AudioParam.linearRampToValueAtTime()

The `linearRampToValueAtTime()` method of the [`AudioParam`](../audioparam) Interface schedules a gradual linear change in the value of the `AudioParam`. The change starts at the time specified for the _previous_ event, follows a linear ramp to the new value given in the `value` parameter, and reaches the new value at the time given in the `endTime` parameter.

## Syntax

    var AudioParam = AudioParam.linearRampToValueAtTime(value, endTime)

### Parameters

value  
A floating point number representing the value the `AudioParam` will ramp to by the given time.

endTime  
A double representing the exact time (in seconds) after the ramping starts that the changing of the value will stop.

### Returns

A reference to this `AudioParam` object. In some browsers older implementations of this interface return void.

## Example

In this example, we have a media source with two control buttons (see the [audio-param repo](https://github.com/mdn/webaudio-examples/tree/master/audio-param) for the source code, or [view the example live](https://mdn.github.io/webaudio-examples/audio-param/).) When these buttons are pressed, `linearRampToValueAtTime()` is used to fade the gain value up to 1.0, and down to 0, respectively. This is pretty useful for fade in/fade out effects, although [`AudioParam.exponentialRampToValueAtTime()`](exponentialramptovalueattime) is often said to be a bit more natural.

    // create audio context
    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    // set basic variables for example
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    var linearRampPlus = document.querySelector('.linear-ramp-plus');
    var linearRampMinus = document.querySelector('.linear-ramp-minus');

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a gain node and set it's gain value to 0.5
    var gainNode = audioCtx.createGain();

    // connect the AudioBufferSourceNode to the gainNode
    // and the gainNode to the destination
    gainNode.gain.setValueAtTime(0, audioCtx.currentTime);
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    // set buttons to do something onclick
    linearRampPlus.onclick = function() {
      gainNode.gain.linearRampToValueAtTime(1.0, audioCtx.currentTime + 2);
    }

    linearRampMinus.onclick = function() {
      gainNode.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 2);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-linearramptovalueattime">Web Audio API<br />
<span class="small">The definition of 'linearRampToValueAtTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`linearRampToValueAtTime`

14

12

25

Does not work (see [bug 1171438](https://bugzil.la/1171438) and [bug 1567777](https://bugzil.la/1567777)).

No

15

6

≤37

18

This sets the target volume at the specified time, but it doesn’t ramp to it, causing this function to behave like `setValueAtTime()`.

25

Does not work (see [bug 1171438](https://bugzil.la/1171438) and [bug 1567777](https://bugzil.la/1567777)).

14

?

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/linearRampToValueAtTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/linearRampToValueAtTime</a>
