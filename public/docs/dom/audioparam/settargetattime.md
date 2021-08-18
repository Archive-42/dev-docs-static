# AudioParam.setTargetAtTime()

The `setTargetAtTime()` method of the [`AudioParam`](../audioparam) interface schedules the start of a gradual change to the `AudioParam` value. This is useful for decay or release portions of ADSR envelopes.

## Syntax

    var paramRef = param.setTargetAtTime(target, startTime, timeConstant);

### Parameters

target  
The value the parameter will start to transition towards at the given start time.

startTime  
The time that the exponential transition will begin, in the same time coordinate system as [`AudioContext.currentTime`](../baseaudiocontext/currenttime). If it is less than or equal to `AudioContext.currentTime`, the parameter will start changing immediately.

timeConstant  
The time-constant value, given in seconds, of an exponential approach to the target value. The larger this value is, the slower the transition will be.

### Returns

A reference to this `AudioParam` object. Some older browser implementations of this interface return void.

## Description

The change starts at the time specified in `startTime` and exponentially moves towards the value given by the `target` parameter. The decay rate as defined by the `timeConstant` parameter is exponential; therefore the value will never reach `target` completely, but after each timestep of length `timeConstant`, the value will have approached `target` by another 1 − *e*<sup> − 1</sup> ≈ 63.2%. For the complete formula (which uses a first-order linear continuous time-invariant system), check the [Web Audio specification](https://webaudio.github.io/web-audio-api/#dom-audioparam-settargetattime).

If you absolutely need to reach the target value by a specific time, you can use [`AudioParam.exponentialRampToValueAtTime()`](exponentialramptovalueattime). However, for mathematical reasons, that method does not work if the current value or the target value is `0`.

### Choosing a good `timeConstant`

As mentioned above, the value changes exponentially, with each `timeConstant` bringing you another 63.2% toward the target value. You don't have to worry about reaching the target value; once you are close enough, any further changes will be imperceptible to a human listener.

Depending on your use case, getting 95% toward the target value may already be enough; in that case, you could set `timeConstant` to one third of the desired duration.

For more details, check the following table on how the value changes from 0% to 100% as the time progresses.

<table><thead><tr class="header"><th>Time since <code>startTime</code></th><th style="text-align: right;">Value</th></tr></thead><tbody><tr class="odd"><td><code>0 * timeConstant</code></td><td style="text-align: right;">0%</td></tr><tr class="even"><td><code>0.5 * timeConstant</code></td><td style="text-align: right;">39.3%</td></tr><tr class="odd"><td><code>1 * timeConstant</code></td><td style="text-align: right;">63.2%</td></tr><tr class="even"><td><code>2 * timeConstant</code></td><td style="text-align: right;">86.5%</td></tr><tr class="odd"><td><code>3 * timeConstant</code></td><td style="text-align: right;">95.0%</td></tr><tr class="even"><td><code>4 * timeConstant</code></td><td style="text-align: right;">98.2%</td></tr><tr class="odd"><td><code>5 * timeConstant</code></td><td style="text-align: right;">99.3%</td></tr><tr class="even"><td><code>n * timeConstant</code></td><td style="text-align: right;"><span class="math inline">1 − <em>e</em><sup> − <em>n</em></sup></span></td></tr></tbody></table>

## Examples

In this example, we have a media source with two control buttons (see the [webaudio-examples repo](https://github.com/mdn/webaudio-examples/blob/master/audio-param/index.html) for the source code, or [view the example live](https://mdn.github.io/webaudio-examples/audio-param/).) When these buttons are pressed, `setTargetAtTime()` is used to fade the gain value up to 1.0, and down to 0, respectively, with the effect starting after 1 second, and the length of time the effect lasts being controlled by the timeConstant.

    // create audio context
    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    // set basic variables for example
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    var atTimePlus = document.querySelector('.at-time-plus');
    var atTimeMinus = document.querySelector('.at-time-minus');

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
    atTimePlus.onclick = function() {
      currGain = 1.0;
      gainNode.gain.setTargetAtTime(1.0, audioCtx.currentTime + 1, 0.5);
    }

    atTimeMinus.onclick = function() {
      currGain = 0;
      gainNode.gain.setTargetAtTime(0, audioCtx.currentTime + 1, 0.5);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-settargetattime">Web Audio API<br />
<span class="small">The definition of 'setTargetAtTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setTargetAtTime`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setTargetAtTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setTargetAtTime</a>
