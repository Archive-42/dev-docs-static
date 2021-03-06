# AudioListener

The `AudioListener` interface represents the position and orientation of the unique person listening to the audio scene, and is used in [audio spatialization](web_audio_api/web_audio_spatialization_basics). All [`PannerNode`](pannernode)s spatialize in relation to the `AudioListener` stored in the [`BaseAudioContext.listener`](baseaudiocontext/listener) attribute.

It is important to note that there is only one listener per context and that it isn't an [`AudioNode`](audionode).

<img src="data:image/png;base64,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" alt="We see the position, up and front vectors of an AudioListener, with the up and front vectors at 90?? from the other." width="634" height="250" />

## Properties

The position, forward, and up value are set and retrieved using different syntaxes. Retrieval is done by accessing, for example, `AudioListener.positionX`, while setting the same property is done with `AudioListener.positionX.value`. This is why these values are not marked read only, which is how they appear in the specification's IDL.

[`AudioListener.positionX`](audiolistener/positionx)  
Represents the horizontal position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.positionY`](audiolistener/positiony)  
Represents the vertical position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.positionZ`](audiolistener/positionz)  
Represents the longitudinal (back and forth) position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.forwardX`](audiolistener/forwardx)  
Represents the horizontal position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.forwardY`](audiolistener/forwardy)  
Represents the vertical position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.forwardZ`](audiolistener/forwardz)  
Represents the longitudinal (back and forth) position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is -1.

[`AudioListener.upX`](audiolistener/upx)  
Represents the horizontal position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.upY`](audiolistener/upy)  
Represents the vertical position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 1.

[`AudioListener.upZ`](audiolistener/upz)  
Represents the longitudinal (back and forth) position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

## Methods

[`AudioListener.setOrientation()`](audiolistener/setorientation) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the orientation of the listener.

[`AudioListener.setPosition()`](audiolistener/setposition) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the position of the listener.

**Note**: Although these methods are deprecated they are currently the only way to set the orientation and position in Firefox, Internet Explorer and Safari.

## Deprecated features

[`AudioListener.dopplerFactor`](audiolistener/dopplerfactor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A double value representing the amount of pitch shift to use when rendering a [doppler effect](https://en.wikipedia.org/wiki/Doppler_effect).

[`AudioListener.speedOfSound`](audiolistener/speedofsound) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a double value representing the speed of sound, in _meters per second_.

In a previous version of the specification, the `dopplerFactor` and `speedOfSound` properties and the `setPosition()` method could be used to control the doppler effect applied to [`AudioBufferSourceNode`](audiobuffersourcenode)s connected downstream ??? these would be pitched up and down according to the relative speed of the [`PannerNode`](pannernode) and the [`AudioListener`](audiolistener). These features had a number of problems:

- Only [`AudioBufferSourceNode`](audiobuffersourcenode)s were pitched up or down, not other source nodes.
- The behavior to adopt when an [`AudioBufferSourceNode`](audiobuffersourcenode) was connected to multiple [`PannerNode`](pannernode)s was unclear.
- Because the velocity of the panner and the listener were not [`AudioParam`](audioparam)s, the pitch modification could not be smoothly applied, resulting in audio glitches.

Because of these issues, these properties and methods have been removed.

The `setOrientation()` and `setPosition()` methods have been replaced by setting their property value equivilents. For example `setPosition(x, y, z)` can be achieved by setting `positionX.value`, `positionY.value`, and `positionZ.value` respectively.

## Example

See [`BaseAudioContext.createPanner()`](baseaudiocontext/createpanner#example) for example code.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audiolistener">Web Audio API<br />
<span class="small">The definition of 'AudioListener' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioListener`

14

12

25

No

15

6

???37

18

25

14

Yes

1.0

`dopplerFactor`

14-56

12-79

25-63

No

15-43

6-14.1

???37-56

18-56

25-63

14-43

6-14.5

1.0-6.0

`forwardX`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`forwardY`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`forwardZ`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`positionX`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`positionY`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`positionZ`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`setOrientation`

14

12

25

No

15

6

???37

18

25

14

Yes

1.0

`setPosition`

14

12

25

No

15

6

???37

18

25

14

Yes

1.0

`speedOfSound`

14-56

12-79

25-63

No

15-43

6-14.1

???37-56

18-56

25-63

14-43

6-14.5

1.0-6.0

`upX`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`upY`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

`upZ`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener</a>
