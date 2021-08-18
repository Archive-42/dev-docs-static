# PannerNode.distanceModel

The `distanceModel` property of the [`PannerNode`](../pannernode) interface is an enumerated value determining which algorithm to use to reduce the volume of the audio source as it moves away from the listener.

The possible values are:

- `linear`: A _linear distance model_ calculating the gain induced by the distance according to:  
  `1 - rolloffFactor * (distance - refDistance) / (maxDistance - refDistance)`
- `inverse`: An _inverse distance model_ calculating the gain induced by the distance according to:  
  `refDistance / (refDistance + rolloffFactor * (Math.max(distance, refDistance) - refDistance))`
- `exponential`: An _exponential distance model_ calculating the gain induced by the distance according to:  
  `pow((Math.max(distance, refDistance) / refDistance, -rolloffFactor)`.

`inverse` is the default value of `distanceModel`.

## Syntax

    var audioCtx = new AudioContext();
    var panner = audioCtx.createPanner();
    panner.distanceModel = 'inverse';

### Value

A enum — see [`DistanceModelType`](https://webaudio.github.io/web-audio-api/#idl-def-DistanceModelType).

## Example

In the following example, you can see an example of how the `createPanner()` method, [`AudioListener`](../audiolistener) and [`PannerNode`](../pannernode) would be used to control audio spatialisation. Generally you will define the position in 3D space that your audio listener and panner (source) occupy initially, and then update the position of one or both of these as the application is used. You might be moving a character around inside a game world for example, and wanting delivery of audio to change realistically as your character moves closer to or further away from a music player such as a stereo. In the example you can see this being controlled by the functions `moveRight()`, `moveLeft()`, etc., which set new values for the panner position via the `PositionPanner()` function.

To see a complete implementation, check out our [panner-node example](https://mdn.github.io/webaudio-examples/panner-node/) ([view the source code](https://github.com/mdn/webaudio-examples/tree/master/panner-node)) — this demo transports you to the 2.5D "Room of metal", where you can play a track on a boom box and then walk around the boom box to see how the sound changes!

Note how we have used some feature detection to either give the browser the newer property values (like [`AudioListener.forwardX`](../audiolistener/forwardx)) for setting position, etc. if it supports those, or older methods (like [`AudioListener.setOrientation()`](../audiolistener/setorientation)) if it still supports those but not the new properties.

    // set up listener and panner position information
    var WIDTH = window.innerWidth;
    var HEIGHT = window.innerHeight;

    var xPos = Math.floor(WIDTH/2);
    var yPos = Math.floor(HEIGHT/2);
    var zPos = 295;

    // define other variables

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var panner = audioCtx.createPanner();
    panner.panningModel = 'HRTF';
    panner.distanceModel = 'inverse';
    panner.refDistance = 1;
    panner.maxDistance = 10000;
    panner.rolloffFactor = 1;
    panner.coneInnerAngle = 360;
    panner.coneOuterAngle = 0;
    panner.coneOuterGain = 0;

    if(panner.orientationX) {
      panner.orientationX.setValueAtTime(1, audioCtx.currentTime);
      panner.orientationY.setValueAtTime(0, audioCtx.currentTime);
      panner.orientationZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      panner.setOrientation(1,0,0);
    }

    var listener = audioCtx.listener;

    if(listener.forwardX) {
      listener.forwardX.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardY.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardZ.setValueAtTime(-1, audioCtx.currentTime);
      listener.upX.setValueAtTime(0, audioCtx.currentTime);
      listener.upY.setValueAtTime(1, audioCtx.currentTime);
      listener.upZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      listener.setOrientation(0,0,-1,0,1,0);
    }

    var source;

    var play = document.querySelector('.play');
    var stop = document.querySelector('.stop');

    var boomBox = document.querySelector('.boom-box');

    var listenerData = document.querySelector('.listener-data');
    var pannerData = document.querySelector('.panner-data');

    leftBound = (-xPos) + 50;
    rightBound = xPos - 50;

    xIterator = WIDTH/150;

    // listener will always be in the same place for this demo

    if(listener.positionX) {
      listener.positionX.setValueAtTime(xPos, audioCtx.currentTime);
      listener.positionY.setValueAtTime(yPos, audioCtx.currentTime);
      listener.positionZ.setValueAtTime(300, audioCtx.currentTime);
    } else {
      listener.setPosition(xPos,yPos,300);
    }

    listenerData.textContent = `Listener data: X ${xPos} Y ${yPos} Z 300`;

    // panner will move as the boombox graphic moves around on the screen
    function positionPanner() {
      if(panner.positionX) {
        panner.positionX.setValueAtTime(xPos, audioCtx.currentTime);
        panner.positionY.setValueAtTime(yPos, audioCtx.currentTime);
        panner.positionZ.setValueAtTime(zPos, audioCtx.currentTime);
      } else {
        panner.setPosition(xPos,yPos,zPos);
      }
      pannerData.textContent = `Panner data: X ${xPos} Y ${yPos} Z ${zPos}`;
    }

**Note**

In terms of working out what position values to apply to the listener and panner, to make the sound appropriate to what the visuals are doing on screen, there is quite a bit of math involved, but you will soon get used to it with a bit of experimentation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-distancemodel">Web Audio API<br />
<span class="small">The definition of 'distanceModel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`distanceModel`

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

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio spatialisation basics](../web_audio_api/web_audio_spatialization_basics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/distanceModel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/distanceModel</a>
