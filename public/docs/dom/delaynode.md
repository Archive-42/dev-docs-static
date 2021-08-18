# DelayNode

The `DelayNode` interface represents a [delay-line](https://en.wikipedia.org/wiki/Digital_delay_line); an [`AudioNode`](audionode) audio-processing module that causes a delay between the arrival of an input data and its propagation to the output. A `DelayNode` always has exactly one input and one output, both with the same amount of channels.

<img src="data:image/png;base64,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" alt="The DelayNode acts as a delay-line, here with a value of 1s." width="774" height="116" />

When creating a graph that has a cycle, it is mandatory to have at least one `DelayNode` in the cycle, or the nodes taking part in the cycle will be muted.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`DelayNode()`](delaynode/delaynode)  
Creates a new instance of an DelayNode object instance. Alternatively, you can use the [`BaseAudioContext.createDelay()`](baseaudiocontext/createdelay) factory method.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)._

[`DelayNode.delayTime`](delaynode/delaytime) <span class="badge inline readonly">Read only </span>  
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing the amount of delay to apply, specified in seconds.

## Methods

_No specific methods; inherits methods from its parent, [`AudioNode`](audionode)._

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#DelayNode">Web Audio API<br />
<span class="small">The definition of 'DelayNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`DelayNode`

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

`DelayNode`

55

Before version 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before version 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DelayNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DelayNode</a>
