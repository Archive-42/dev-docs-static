# ConstantSourceNode

The `ConstantSourceNode` interface—part of the Web Audio API—represents an audio source (based upon [`AudioScheduledSourceNode`](audioscheduledsourcenode)) whose output is single unchanging value. This makes it useful for cases in which you need a constant value coming in from an audio source. In addition, it can be used like a constructible [`AudioParam`](audioparam) by automating the value of its [`offset`](constantsourcenode/offset) or by connecting another node to it; see [Controlling multiple parameters with ConstantSourceNode](web_audio_api/controlling_multiple_parameters_with_constantsourcenode).

A `ConstantSourceNode` has no inputs and exactly one monaural (one-channel) output. The output's value is always the same as the value of the [`offset`](constantsourcenode/offset) parameter.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr></tbody></table>

## Constructor

[`ConstantSourceNode()`](constantsourcenode/constantsourcenode)  
Creates and returns a new `ConstantSourceNode` instance, optionally specifying an object which establishes initial values for the object's properties. You can also create a `ConstantSourceNode` whose properties are initialized to their default values by calling [`AudioContext.createConstantSource()`](baseaudiocontext/createconstantsource).

## Properties

_Inherits properties from its parent interface, [`AudioScheduledSourceNode`](audioscheduledsourcenode), and adds the following properties:_

[`offset`](constantsourcenode/offset)  
An [`AudioParam`](audioparam) which specifies the value that this source continuously outputs. The default value is 1.0.

### Event handlers

_Inherits event handlers from its parent interface, [`AudioScheduledSourceNode`](audioscheduledsourcenode)._

Some browsers' implementations of this event handler are part of the [`AudioScheduledSourceNode`](audioscheduledsourcenode) interface.

[`onended`](audioscheduledsourcenode/onended)  
Fired whenever the [`ConstantSourceNode`](constantsourcenode) data has stopped playing.

## Methods

_Inherits methods from its parent interface, [`AudioScheduledSourceNode`](audioscheduledsourcenode)._

Some browsers' implementations of these methods are part of the [`AudioScheduledSourceNode`](audioscheduledsourcenode) interface.

[`start()`](audioscheduledsourcenode/start)  
Schedules a sound to playback at an exact time.

[`stop()`](audioscheduledsourcenode/stop)  
Schedules a sound to stop playback at an exact time.

## Example

In the article [Controlling multiple parameters with ConstantSourceNode](web_audio_api/controlling_multiple_parameters_with_constantsourcenode), a `ConstantSourceNode` is created to allow one slider control to change the gain on two [`GainNode`](gainnode)s. The three nodes are set up like this:

    gainNode2 = context.createGain();
    gainNode3 = context.createGain();
    gainNode2.gain.value = gainNode3.gain.value = 0.5;
    volumeSliderControl.value = gainNode2.gain.value;

    constantNode = context.createConstantSource();
    constantNode.connect(gainNode2.gain);
    constantNode.connect(gainNode3.gain);
    constantNode.start();

    gainNode2.connect(context.destination);
    gainNode3.connect(context.destination);

This code starts by creating the gain nodes and setting them and the volume control that will adjust their value all to 0.5. Then the `ConstantSourceNode` is created by calling [`AudioContext.createConstantSource()`](baseaudiocontext/createconstantsource), and the gain parameters of each of the two gain nodes are connected to the `ConstantSourceNode`. After starting the constant source by calling its [`start()`](audioscheduledsourcenode/start) method. Finally, the two gain nodes are connected to the audio destination (typically speakers or headphones).

Now, whenever the value of [`constantNode.offset`](constantsourcenode/offset) changes, the gain on both `gainNode2` and `gainNode3` will change to have that same value.

To see this example in action, as well as to read the rest of the code from which these snippets were derived, see [Controlling multiple parameters with ConstantSourceNode.](web_audio_api/controlling_multiple_parameters_with_constantsourcenode)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#ConstantSourceNode">Web Audio API<br />
<span class="small">The definition of 'ConstantSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ConstantSourceNode`

56

79

52

No

43

14.1

56

56

52

43

14.5

6.0

`ConstantSourceNode`

56

79

52

No

43

14.1

56

56

52

43

14.5

6.0

`offset`

56

79

52

No

No

14.1

No

No

52

No

14.5

No

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [`AudioScheduledSourceNode`](audioscheduledsourcenode)
- [`AudioNode`](audionode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode</a>
