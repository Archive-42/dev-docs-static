PannerNode.positionY
====================

The `positionY` property of the [`PannerNode`](../pannernode) interface specifies the Y coordinate of the audio source's position in 3D Cartesian coordinates, corresponding to the *vertical* axis (top-bottom). The complete vector is defined by the position of the audio source, given as ([`positionX`](positionx), [`positionY`](positiony), [`positionZ`](positionz)), and the orientation of the audio source (that is, the direction in which it's facing), given as ([`orientationX`](orientationx), [`orientationY`](orientationy), [`orientationZ`](orientationz)).

Depending on the directionality of the sound (as specified using the attributes [`coneInnerAngle`](coneinnerangle), [`coneOuterAngle`](coneouterangle), and [`codeOuterGain`](coneoutergain)), the orientation of the sound may alter the perceived volume of the sound as it's being played. If the sound is pointing toward the listener, it will be louder than if the sound is pointed away from the listener.

The [`AudioParam`](../audioparam) contained by this property is read only; however, you can still change the value of the parameter by assigning a new value to its [`AudioParam.value`](../audioparam/value) property.

Syntax
------

    var positionY = PannerNode.positionY;

    PannerNode.positionY.value = newPositionY;

### Value

An [`AudioParam`](../audioparam) whose `value` is the Y coordinate of the audio source's position, in 3D Cartesian coordinates.

Example
-------

The following example starts an oscillator and pans it above the listener after 1 second, below the listener after 2 seconds, and back to the center after 3 seconds. Note that in this case, the change will mainly affect the timbre of the oscillator, as it's a simple mono wave.

    const context = new AudioContext();

    const osc = new OscillatorNode(context);
    const panner = new PannerNode(context);
    panner.panningModel = 'HRTF';

    panner.positionY.setValueAtTime(1, context.currentTime + 1);
    panner.positionY.setValueAtTime(-1, context.currentTime + 2);
    panner.positionY.setValueAtTime(0, context.currentTime + 3);

    osc.connect(panner)
       .connect(context.destination);

    osc.start(0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-positiony">Web Audio API<br />
<span class="small">The definition of 'positionY' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`positionY`

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

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)
-   [Web Audio spatialisation basics](../web_audio_api/web_audio_spatialization_basics)
-   [`PannerNode`](../pannernode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY</a>
