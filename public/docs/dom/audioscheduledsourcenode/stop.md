# AudioScheduledSourceNode.stop()

The `stop()` method on [`AudioScheduledSourceNode`](../audioscheduledsourcenode) schedules a sound to cease playback at the specified time. If no time is specified, then the sound stops playing immediately.

Each time you call `stop()` on the same node, the specified time replaces any previously-scheduled stop time that hasn't occurred yet. If the node has already stopped, this method has no effect.

**Note:** If a scheduled stop time occurs before the node's scheduled start time, the node never starts to play.

## Syntax

    AudioScheduledSourceNode.stop([when]);

### Parameters

`when` <span class="badge inline optional">Optional</span>  
The time, in seconds, at which the sound should stop playing. This value is specified in the same time coordinate system as the [`AudioContext`](../audiocontext) is using for its [`currentTime`](../baseaudiocontext/currenttime) attribute. Omitting this parameter, specifying a value of 0, or passing a negative value causes the sound to stop playback immediately.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

`InvalidStateNode`  
The node has not been started by calling [`start()`](start).

`RangeError`  
The value specified for `when` is negative.

## Example

This example demonstrates starting an oscillator node, scheduled to begin playing at once and to stop playing in one second. The stop time is determined by taking the audio context's current time from [`AudioContext.currentTime`](../baseaudiocontext/currenttime) and adding 1 second.

    context = new AudioContext();
    osc = context.createOscillator();
    osc.connect(context.destination);

    /* Let's play a sine wave for one second. */

    osc.start();
    osc.stop(context.currentTime + 1);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-stop">Web Audio API<br />
<span class="small">The definition of 'stop()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`stop`

24

12

25

No

15

6.1

≤37

25

25

14

7

1.5

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [`start()`](start)
- [`AudioScheduledSourceNode`](../audioscheduledsourcenode)
- [`AudioBufferSourceNode`](../audiobuffersourcenode)
- [`ConstantSourceNode`](../constantsourcenode)
- [`OscillatorNode`](../oscillatornode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/stop</a>
