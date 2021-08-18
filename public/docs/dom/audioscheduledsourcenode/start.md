# AudioScheduledSourceNode.start()

The `start()` method on [`AudioScheduledSourceNode`](../audioscheduledsourcenode) schedules a sound to begin playback at the specified time. If no time is specified, then the sound begins playing immediately.

## Syntax

    AudioScheduledSourceNode.start([when [, offset [, duration]]]);

### Parameters

`when` <span class="badge inline optional">Optional</span>  
The time, in seconds, at which the sound should begin to play. This value is specified in the same time coordinate system as the [`AudioContext`](../audiocontext) is using for its [`currentTime`](../baseaudiocontext/currenttime) attribute. A value of 0 (or omitting the `when` parameter entirely) causes the sound to start playback immediately.

`offset` <span class="badge inline optional">Optional</span>  
A floating-point number indicating the offset, in seconds, into the audio buffer where playback should begin. If 0 is passed then the playback will start from the beginning.

`duration` <span class="badge inline optional">Optional</span>  
A floating-point number indicating the duration, in seconds, to be played. If no value is passed then the duration will be equal to the length of the audio buffer minus the offset value

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

`InvalidStateNode`  
The node has already been started. This error occurs even if the node is no longer running because of a prior call to [`stop()`](stop).

`RangeError`  
The value specified for `when` is negative.

## Example

This example demonstrates how to create an [`OscillatorNode`](../oscillatornode) which is scheduled to start playing in 2 seconds and stop playing 1 second after that. The times are calculated by adding the desired number of seconds to the context's current time stamp returned by [`AudioContext.currentTime`](../baseaudiocontext/currenttime).

    context = new AudioContext();
    osc = context.createOscillator();
    osc.connect(context.destination);

    /* Schedule the start and stop times for the oscillator */

    osc.start(context.currentTime + 2);
    osc.stop(context.currentTime + 3);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-start">Web Audio API<br />
<span class="small">The definition of 'start()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`start`

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
- [`stop()`](stop)
- [`AudioScheduledSourceNode`](../audioscheduledsourcenode)
- [`AudioBufferSourceNode`](../audiobuffersourcenode)
- [`ConstantSourceNode`](../constantsourcenode)
- [`OscillatorNode`](../oscillatornode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/start</a>
