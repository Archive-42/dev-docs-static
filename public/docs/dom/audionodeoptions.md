# AudioNodeOptions

The `AudioNodeOptions` dictionary of the [Web Audio API](web_audio_api) specifies options that can be used when creating new [`AudioNode`](audionode) objects.

`AudioNodeOptions` is inherited from by the option objects of the different types of audio node constructors. See for example [`AnalyserNode.AnalyserNode`](analysernode/analysernode) or [`GainNode.GainNode`](gainnode/gainnode).

## Syntax

    var audioNodeOptions = {
      "channelCount" : 2,
      "channelCountMode" : "max",
      "channelInterpretation" : "discrete"
    }

### Properties

`channelCount` <span class="badge inline optional">Optional</span>  
Represents an integer used to determine how many channels are used when [up-mixing and down-mixing](web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) connections to any inputs to the node. (See [`AudioNode.channelCount`](audionode/channelcount) for more information.) Its usage and precise definition depend on the value of <span class="page-not-created">`AudioNodeOptions.channelCountMode`</span>.

`channelCountMode` <span class="badge inline optional">Optional</span>  
Represents an enumerated value describing the way channels must be matched between the node's inputs and outputs. (See [`AudioNode.channelCountMode`](audionode/channelcountmode) for more information including default values.)

`channelInterpretation` <span class="badge inline optional">Optional</span>  
Represents an enumerated value describing the meaning of the channels. This interpretation will define how audio [up-mixing and down-mixing](web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) will happen.  
The possible values are `"speakers"` or `"discrete"`. (See [`AudioNode.channelCountMode`](audionode/channelcountmode) for more information including default values.)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dictdef-audionodeoptions">Web Audio API<br />
<span class="small">The definition of 'AudioNodeOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioNodeOptions`

55

≤79

53

No

42

?

55

55

53

42

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNodeOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNodeOptions</a>
