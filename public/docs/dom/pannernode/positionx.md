# PannerNode.positionX

The `positionX` property of the [`PannerNode`](../pannernode) interface specifies the X coordinate of the audio source's position in 3D Cartesian coordinates, corresponding to the _horizontal_ axis (left-right).

The complete vector is defined by the position of the audio source, given as ([`positionX`](positionx), [`positionY`](positiony), [`positionZ`](positionz)), and the orientation of the audio source (that is, the direction in which it's facing), given as ([`orientationX`](orientationx), [`orientationY`](orientationy), [`orientationZ`](orientationz)).

Depending on the directionality of the sound (as specified using the attributes [`coneInnerAngle`](coneinnerangle), [`coneOuterAngle`](coneouterangle), and [`codeOuterGain`](coneoutergain)), the orientation of the sound may alter the perceived volume of the sound as it's being played. If the sound is pointing toward the listener, it will be louder than if the sound is pointed away from the listener.

The [`AudioParam`](../audioparam) contained by this property is read only; however, you can still change the value of the parameter by assigning a new value to its [`AudioParam.value`](../audioparam/value) property.

## Syntax

    var positionX = PannerNode.positionX;

    PannerNode.positionX.value = newPositionX;

### Value

An [`AudioParam`](../audioparam) whose `value` is the X coordinate of the audio source's position, in 3D Cartesian coordinates. The default value is 0.

## Example

The following example starts an oscillator, and pans it to the left after 1 second, to the right after 2 seconds, and back to the center after 3 seconds.

    const context = new AudioContext();

    const osc = new OscillatorNode(context);
    const panner = new PannerNode(context);

    panner.positionX.setValueAtTime(-1, context.currentTime + 1);
    panner.positionX.setValueAtTime(1, context.currentTime + 2);
    panner.positionX.setValueAtTime(0, context.currentTime + 3);

    osc.connect(panner)
       .connect(context.destination);

    osc.start(0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-positionx">Web Audio API<br />
<span class="small">The definition of 'positionX' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`positionX`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio spatialisation basics](../web_audio_api/web_audio_spatialization_basics)
- [`PannerNode`](../pannernode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionX</a>
