# DelayNode.delayTime

The `delayTime` property of the [`DelayNode`](../delaynode) interface is an [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam) representing the amount of delay to apply.

`delayTime` is expressed in seconds, its minimal value is `0`, and its maximum value is defined by the `maxDelayTime` argument of the [`BaseAudioContext.createDelay`](../baseaudiocontext/createdelay) method that created it.

## Syntax

    var audioCtx = new AudioContext();
    var myDelay = audioCtx.createDelay(5.0);
    myDelay.delayTime.value = 3.0;

**Note**: Though the [`AudioParam`](../audioparam) returned is read-only, the value it represents is not.

### Value

An [`AudioParam`](../audioparam).

## Example

We have created a simple example that allows you to play three different samples on a constant loop — see [create-delay](https://chrisdavidmills.github.io/create-delay/) (you can also [view the source code](https://github.com/chrisdavidmills/create-delay)). If you just press the play buttons, the loops will start immediately; if you slide the sliders up to the right, then press the play buttons, a delay will be introduced, so the looping sounds don't start playing for a short amount of time.

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var synthDelay = audioCtx.createDelay(5.0);

      ...

    var synthSource;

    playSynth.onclick = function() {
      synthSource = audioCtx.createBufferSource();
      synthSource.buffer = buffers[2];
      synthSource.loop = true;
      synthSource.start();
      synthSource.connect(synthDelay);
      synthDelay.connect(destination);
      this.setAttribute('disabled', 'disabled');
    }

    stopSynth.onclick = function() {
      synthSource.disconnect(synthDelay);
      synthDelay.disconnect(destination);
      synthSource.stop();
      playSynth.removeAttribute('disabled');
    }

    ...

    var delay1;
    rangeSynth.oninput = function() {
      delay1 = rangeSynth.value;
      synthDelay.delayTime.setValueAtTime(delay1, audioCtx.currentTime);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-delaynode-delaytime">Web Audio API<br />
<span class="small">The definition of 'delayTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`delayTime`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DelayNode/delayTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DelayNode/delayTime</a>
