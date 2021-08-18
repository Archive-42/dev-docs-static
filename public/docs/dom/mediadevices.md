MediaDevices
============

The `MediaDevices` interface provides access to connected media input devices like cameras and microphones, as well as screen sharing. In essence, it lets you obtain access to any hardware source of media data.

Properties
----------

*Inherits properties from its parent interface, [`EventTarget`](eventtarget).*

Events
------

[`devicechange`](mediadevices/devicechange_event)  
Fired when a media input or output device is attached to or removed from the user's computer.  
Also available via the [`ondevicechange`](mediadevices/ondevicechange) property.

Methods
-------

*Inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`enumerateDevices()`](mediadevices/enumeratedevices)  
Obtains an array of information about the media input and output devices available on the system.

[`getSupportedConstraints()`](mediadevices/getsupportedconstraints)  
Returns an object conforming to [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints) indicating which constrainable properties are supported on the [`MediaStreamTrack`](mediastreamtrack) interface. See [Capabilities and constraints](media_streams_api#capabilities_and_constraints) in [Media Capture and Streams API (Media Stream)](media_streams_api) to learn more about constraints and how to use them.

[`getDisplayMedia()`](mediadevices/getdisplaymedia)  
Prompts the user to select a display or portion of a display (such as a window) to capture as a [`MediaStream`](mediastream) for sharing or recording purposes. Returns a promise that resolves to a `MediaStream`.

[`getUserMedia()`](mediadevices/getusermedia)  
With the user's permission through a prompt, turns on a camera and/or a microphone on the system and provides a [`MediaStream`](mediastream) containing a video track and/or an audio track with the input.

Example
-------

    'use strict';

    // Put variables in global scope to make them available to the browser console.
    var video = document.querySelector('video');
    var constraints = window.constraints = {
      audio: false,
      video: true
    };
    var errorElement = document.querySelector('#errorMsg');

    navigator.mediaDevices.getUserMedia(constraints)
    .then(function(stream) {
      var videoTracks = stream.getVideoTracks();
      console.log('Got stream with constraints:', constraints);
      console.log('Using video device: ' + videoTracks[0].label);
      stream.onremovetrack = function() {
        console.log('Stream ended');
      };
      window.stream = stream; // make variable available to browser console
      video.srcObject = stream;
    })
    .catch(function(error) {
      if (error.name === 'ConstraintNotSatisfiedError') {
        errorMsg('The resolution ' + constraints.video.width.exact + 'x' +
            constraints.video.height.exact + ' px is not supported by your device.');
      } else if (error.name === 'PermissionDeniedError') {
        errorMsg('Permissions have not been granted to use your camera and ' +
          'microphone, you need to allow the page access to your devices in ' +
          'order for the demo to work.');
      }
      errorMsg('getUserMedia error: ' + error.name, error);
    });

    function errorMsg(msg, error) {
      errorElement.innerHTML += '<p>' + msg + '</p>';
      if (typeof error !== 'undefined') {
        console.error(error);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#mediadevices">Media Capture and Streams<br />
<span class="small">The definition of 'MediaDevices' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaDevices`

47

12

33

No

30

11

47

47

36

30

11

5.0

`devicechange_event`

57

12

52

No

34

11

No

No

?

43

11

No

`enumerateDevices`

47

12

39

63

Prior to Firefox 63, `enumerateDevices()` only returned input devices. Starting with Firefox 63, output devices are also included if the `media.setsinkid.enabled` preference is enabled.

No

34

11

47

47

39

63

Prior to Firefox 63, `enumerateDevices()` only returned input devices. Starting with Firefox 63, output devices are also included if the `media.setsinkid.enabled` preference is enabled.

34

11

5.0

`getDisplayMedia`

72

79

17

Available as a member of `Navigator` instead of `MediaDevices`.

66

33-66

Since Firefox 33 you can capture screen data using `getUserMedia()`, with a `video` constraint called `mediaSource`. Prior to 52 it relied on a client-configurable list of allowed sites.

No

60

13

No

API is available, but will always fail with `NotAllowedError`.

No

No

API is available, but will always fail with `NotAllowedError`.

No

No

No

`getSupportedConstraints`

53

12

44

No

40

11

53

52

50

41

11

6.0

`getUserMedia`

53

If you need this capability before version 53, refer to `navigator.webkitGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.

12

36

\["If you need this capability before version 36, refer to `navigator.mozGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.", "Before Firefox 55, `getUserMedia()` incorrectly returns `NotSupportedError` when the list of constraints specified is empty, or has all constraints set to `false`. Starting in Firefox 55, this situation now correctly calls the failure handler with a `TypeError`.", "When using the Firefox-specific `video` constraint called `mediaSource` to request display capture, Firefox 66 and later consider values of `screen` and `window` to both cause a list of screens *and* windows to be shown.", "Starting in Firefox 66, `getUserMedia()` can no longer be used in sandboxed `<iframe>`s or `data` URLs entered in the address bar by the user."\]

No

40

If you need this capability before version 40, refer to `navigator.webkitGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.

11

53

53

If you need this capability before version 53, refer to `navigator.webkitGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.

36

\["If you need this capability before version 36, refer to `navigator.mozGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.", "Before Firefox 55, `getUserMedia()` incorrectly returns `NotSupportedError` when the list of constraints specified is empty, or has all constraints set to `false`. Starting in Firefox 55, this situation now correctly calls the failure handler with a `TypeError`.", "When using the Firefox-specific `video` constraint called `mediaSource` to request display capture, Firefox 66 and later consider values of `screen` and `window` to both cause a list of screens *and* windows to be shown.", "Starting in Firefox 66, `getUserMedia()` can no longer be used in sandboxed `<iframe>`s or `data` URLs entered in the address bar by the user."\]

41

If you need this capability before version 41, refer to `navigator.webkitGetUserMedia`, a prefixed form of the deprecated [`navigator.getUserMedia`](https://developer.mozilla.org/docs/Web/API/Navigator/getUserMedia) API.

11

6.0

`ondevicechange`

57

12

52

No

34

11

No

No

Yes

34

11

No

`stereo_audio_capture`

?

?

55

No

?

No

?

?

No

?

No

?

See also
--------

-   [Media Capture and Streams API](media_streams_api): The API this interface is part of.
-   [Screen Capture API](screen_capture_api): The API defining the [`getDisplayMedia()`](mediadevices/getdisplaymedia) method.
-   [WebRTC API](webrtc_api)
-   [`Navigator.mediaDevices`](navigator/mediadevices): Returns a reference to a `MediaDevices` object that can be used to access devices.
-   [CameraCaptureJS:](https://github.com/chrisjohndigital/CameraCaptureJS) HTML5 video capture and playback using `MediaDevices` and the MediaStream Recording API ([source on GitHub](https://github.com/chrisjohndigital/CameraCaptureJS))
-   [OpenLang](https://github.com/chrisjohndigital/OpenLang): HTML5 video language lab web application using `MediaDevices` and the MediaStream Recording API for video recording ([source on GitHub](https://github.com/chrisjohndigital/OpenLang))

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices</a>
