# AudioContext.getOutputTimestamp()

The `getOutputTimestamp()` property of the [`AudioContext`](../audiocontext) interface returns a new `AudioTimestamp` object containing two audio timestamp values relating to the current audio context.

The two values are as follows:

- `AudioTimestamp.contextTime`: The time of the sample frame currently being rendered by the audio output device (i.e., output audio stream position), in the same units and origin as the context's [`AudioContext.currentTime`](../baseaudiocontext/currenttime). Basically, this is the time after the audio context was first created.
- `AudioTimestamp.performanceTime`: An estimation of the moment when the sample frame corresponding to the stored `contextTime` value was rendered by the audio output device, in the same units and origin as [`performance.now()`](../performance/now). This is the time after the document containing the audio context was first rendered.

## Syntax

    var timestamp = context.getOutputTimestamp()

### Parameters

None.

### Returns

An `AudioTimestamp` object, which has the following properties.

- `contextTime`: A point in the time coordinate system of the [`currentTime`](../baseaudiocontext/currenttime) for the `BaseAudioContext`; the time after the audio context was first created.
- `performanceTime`: A point in the time coordinate system of a `Performance` interface; the time after the document containing the audio context was first rendered

## Examples

In the following code we start to play an audio file after a play button is clicked, and start off a `requestAnimationFrame` loop running, which constantly outputs the `contextTime` and `performanceTime`.

You can see full code of this [example at output-timestamp](https://github.com/mdn/webaudio-examples/blob/master/output-timestamp/index.html) ([see it live also](https://mdn.github.io/webaudio-examples/output-timestamp/)).

    play.addEventListener('click', () => {
      if(!audioCtx) {
        audioCtx = new window.AudioContext();
      }

      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');

      rAF = requestAnimationFrame(outputTimestamps);
    });

    stop.addEventListener('click', () => {
      source.stop(0);
      play.removeAttribute('disabled');
      cancelAnimationFrame(rAF);
    });

    // function to output timestamps

    function outputTimestamps() {
      let ts = audioCtx.getOutputTimestamp()
      console.log('Context time: ' + ts.contextTime + ' | Performance time: ' + ts.performanceTime);
      rAF = requestAnimationFrame(outputTimestamps);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-getoutputtimestamp">Web Audio API<br />
<span class="small">The definition of 'getOutputTimestamp()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getOutputTimestamp`

57

79

70

No

44

14.1

57

57

No

43

14.5

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/getOutputTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/getOutputTimestamp</a>
