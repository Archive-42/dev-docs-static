# PannerNode.PannerNode()

The `PannerNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`PannerNode`](../pannernode) object instance.

## Syntax

    var myPanner = new PannerNode(context, options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

_context_  
A [`BaseAudioContext`](../baseaudiocontext) representing the audio context you want the node to be associated with.

_options_ <span class="badge inline optional">Optional</span>  
A `PannerOptions` dictionary object defining the properties you want the `PannerNode` to have (It also inherits the options defined in the [AudioNodeOptions](https://webaudio.github.io/web-audio-api/#idl-def-AudioNodeOptions) dictionary.):

- `panningModel`: The [`PannerNode.panningModel`](panningmodel) you want the [`PannerNode`](../pannernode) to have (the default is `equalpower`.)
- `distanceModel`: The [`PannerNode.distanceModel`](distancemodel) you want the [`PannerNode`](../pannernode) to have (the default is `inverse`.)
- `positionX`: The [`PannerNode.positionX`](positionx) you want the [`PannerNode`](../pannernode) to have (the default is `0`.)
- `positionY`: The [`PannerNode.positionY`](positiony) you want the [`PannerNode`](../pannernode) to have (the default is `0`.)
- `positionZ`: The [`PannerNode.positionZ`](positionz) you want the [`PannerNode`](../pannernode) to have (the default is `0`.)
- `orientationX`: The [`PannerNode.orientationX`](orientationx) you want the [`PannerNode`](../pannernode) to have (the default is `1`.)
- `orientationY`: The [`PannerNode.orientationY`](orientationy) you want the [`PannerNode`](../pannernode) to have (the default is `0`.)
- `orientationZ`: The [`PannerNode.orientationZ`](orientationz) you want the [`PannerNode`](../pannernode) to have (the default is `0`.)
- `refDistance`: The [`PannerNode.refDistance`](refdistance) you want the [`PannerNode`](../pannernode) to have. The default is `1`, and negative values are not allowed.
- `maxDistance`: The [`PannerNode.maxDistance`](maxdistance) you want the [`PannerNode`](../pannernode) to have. The default is `10000`, and non-positive values are not allowed.
- `rollOffFactor`: The [`PannerNode.rollOffFactor`](rollofffactor) you want the [`PannerNode`](../pannernode) to have. The default is `1`, and negative values are not allowed.
- `coneInnerAngle`: The [`PannerNode.coneInnerAngle`](coneinnerangle) you want the [`PannerNode`](../pannernode) to have (the default is `360`.)
- `coneOuterAngle`: The [`PannerNode.coneOuterAngle`](coneouterangle) you want the [`PannerNode`](../pannernode) to have (the default is `360`.)
- `coneOuterGain`: The [`PannerNode.coneOuterGain`](coneoutergain) you want the [`PannerNode`](../pannernode) to have. The default is `0`, and its value can be in the range 0–1.

### Return value

A new [`PannerNode`](../pannernode) object instance.

### Exceptions

`RangeError`  
The `refDistance`, `maxDistance`, or `rolloffFactor` properties have been given a value that is outside the accepted range.

`InvalidStateError`  
The `coneOuterGain` property has been given a value outside the accepted range (0–1).

## Example

    var ctx = new AudioContext();

    var options = {
      positionX : 1,
      maxDistance: 5000
    }

    var myPanner = new PannerNode(ctx, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-pannernode">Web Audio API<br />
<span class="small">The definition of 'PannerNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`PannerNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/PannerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/PannerNode</a>
