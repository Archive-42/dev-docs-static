# AudioParam

The Web Audio API's `AudioParam` interface represents an audio-related parameter, usually a parameter of an [`AudioNode`](audionode) (such as [`GainNode.gain`](gainnode/gain)). An `AudioParam` can be set to a specific value or a change in value, and can be scheduled to happen at a specific time and following a specific pattern.

There are two kinds of `AudioParam`, _a-rate_ and _k-rate_ parameters:

- <span id="a-rate">An _a-rate_ `AudioParam` takes the current audio parameter value for each [sample frame](web_audio_api/basic_concepts_behind_web_audio_api#audio_buffers.3a_frames.2c_samples_and_channels) of the audio signal.</span>
- <span id="k-rate">A _k-rate_ `AudioParam` uses the same initial audio parameter value for the whole block processed, that is 128 sample frames. In other words, the same value applies to every frame in the audio as it's processed by the node.</span>

Each [`AudioNode`](audionode) defines which of its parameters are _a-rate_ or _k-rate_ in the spec.

Each `AudioParam` has a list of events, initially empty, that define when and how values change. When this list is not empty, changes using the `AudioParam.value` attributes are ignored. This list of events allows us to schedule changes that have to happen at very precise times, using arbitrary timelime-based automation curves. The time used is the one defined in [`AudioContext.currentTime`](baseaudiocontext/currenttime).

## Properties

[`AudioParam.defaultValue`](audioparam/defaultvalue) <span class="badge inline readonly">Read only </span>  
Represents the initial volume of the attribute as defined by the specific [`AudioNode`](audionode) creating the `AudioParam`.

[`AudioParam.maxValue`](audioparam/maxvalue) <span class="badge inline readonly">Read only </span>  
Represents the maximum possible value for the parameter's nominal (effective) range.

[`AudioParam.minValue`](audioparam/minvalue) <span class="badge inline readonly">Read only </span>  
Represents the minimum possible value for the parameter's nominal (effective) range.

[`AudioParam.value`](audioparam/value)  
Represents the parameter's current value as of the current time; initially set to the value of [`defaultValue`](audioparam/defaultvalue).

## Methods

[`AudioParam.setValueAtTime()`](audioparam/setvalueattime)  
Schedules an instant change to the value of the `AudioParam` at a precise time, as measured against [`AudioContext.currentTime`](baseaudiocontext/currenttime). The new value is given by the `value` parameter.

[`AudioParam.linearRampToValueAtTime()`](audioparam/linearramptovalueattime)  
Schedules a gradual linear change in the value of the `AudioParam`. The change starts at the time specified for the _previous_ event, follows a linear ramp to the new value given in the `value` parameter, and reaches the new value at the time given in the `endTime` parameter.

[`AudioParam.exponentialRampToValueAtTime()`](audioparam/exponentialramptovalueattime)  
Schedules a gradual exponential change in the value of the `AudioParam`. The change starts at the time specified for the _previous_ event, follows an exponential ramp to the new value given in the `value` parameter, and reaches the new value at the time given in the `endTime` parameter.

[`AudioParam.setTargetAtTime()`](audioparam/settargetattime)  
Schedules the start of a change to the value of the `AudioParam`. The change starts at the time specified in `startTime` and exponentially moves towards the value given by the `target` parameter. The exponential decay rate is defined by the `timeConstant` parameter, which is a time measured in seconds.

[`AudioParam.setValueCurveAtTime()`](audioparam/setvaluecurveattime)  
Schedules the values of the `AudioParam` to follow a set of values, defined by an array of floating-point numbers scaled to fit into the given interval, starting at a given start time and spanning a given duration of time.

[`AudioParam.cancelScheduledValues()`](audioparam/cancelscheduledvalues)  
Cancels all scheduled future changes to the `AudioParam`.

[`AudioParam.cancelAndHoldAtTime()`](audioparam/cancelandholdattime)  
Cancels all scheduled future changes to the `AudioParam` but holds its value at a given time until further changes are made using other methods.

## Examples

First, a basic example showing a [`GainNode`](gainnode) having its `gain` value set. `gain` is an example of an a-rate AudioParam, as the value can potentially be set differently for each sample frame of the audio.

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0;

Next, an example showing a [`DynamicsCompressorNode`](dynamicscompressornode) having some param values manipulated. These are examples of k-rate AudioParam's, as the values are set for the entire audio block at once.

    var compressor = audioCtx.createDynamicsCompressor();
    compressor.threshold.setValueAtTime(-50, audioCtx.currentTime);
    compressor.knee.setValueAtTime(40, audioCtx.currentTime);
    compressor.ratio.setValueAtTime(12, audioCtx.currentTime);
    compressor.attack.setValueAtTime(0, audioCtx.currentTime);
    compressor.release.setValueAtTime(0.25, audioCtx.currentTime);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioParam">Web Audio API<br />
<span class="small">The definition of 'AudioParam' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioParam`

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

`automationRate`

68

79

No

No

55

14

68

68

No

48

14

10.0

`cancelAndHoldAtTime`

57

79

No

No

44

14.1

57

57

No

43

14.5

7.0

`cancelScheduledValues`

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

`defaultValue`

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

`exponentialRampToValueAtTime`

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

Yes

1.0

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

`maxValue`

52

79

53

No

39

6

52

52

53

41

Yes

6.0

`minValue`

52

79

53

No

39

6

52

52

53

41

Yes

6.0

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

`setValueCurveAtTime`

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

`value`

14

12

25

Prior to Firefox 69, `value` did not take into account scheduled or gradiated changes to the parameter's value; instead, only explicitly set values were returned.

No

15

6

≤37

18

25

Firefox for Android does not currently take into account scheduled or gradiated changes to the parameter's value; only the initial value or the most recent explicitly set value is returned.

14

Yes

1.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam</a>
