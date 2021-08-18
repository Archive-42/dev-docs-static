# Navigator.getUserMedia()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `Navigator.getUserMedia()` method prompts the user for permission to use up to one video input device (such as a camera or shared screen) and up to one audio input device (such as a microphone) as the source for a [`MediaStream`](../mediastream).

If permission is granted, a `MediaStream` whose video and/or audio tracks come from those devices is delivered to the specified success callback. If permission is denied, no compatible input devices exist, or any other error condition occurs, the error callback is executed with a <span class="page-not-created">`MediaStreamError`</span> object describing what went wrong. If the user instead doesn't make a choice at all, neither callback is executed.

This is a legacy method. Please use the newer [`navigator.mediaDevices.getUserMedia()`](../mediadevices/getusermedia) instead. While technically not deprecated, this old callback version is marked as such, since the specification strongly encourages using the newer promise returning version.

## Syntax

    navigator.getUserMedia(constraints, successCallback, errorCallback);

### Parameters

`constraints`  
A [`MediaStreamConstraints`](../mediastreamconstraints) object specifying the types of media to request, along with any requirements for each type. For details, see the [constraints](../mediadevices/getusermedia#parameters) section under the modern [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia) method, as well as the article [Capabilities, constraints, and settings](../media_streams_api/constraints).

`successCallback`  
A function which is invoked when the request for media access is approved. The function is called with one parameter: the [`MediaStream`](../mediastream) object that contains the media stream. Your callback can then assign the stream to the desired object (such as an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element), as shown in the following example:

    function(stream) {
       var video = document.querySelector('video');
       video.srcObject = stream;
       video.onloadedmetadata = function(e) {
          // Do something with the video here.
       };
    }

`errorCallback`  
When the call fails, the function specified in the `errorCallback` is invokedwith a <span class="page-not-created">`MediaStreamError`</span> object as its sole argument; this object is modeled on [`DOMException`](../domexception). See [Errors](#errors) below for a list of the errors which can occur.

### Return value

<span class="page-not-created">`undefined`</span>.

### Errors

{{page("/en-US/docs/Web/API/MediaDevices/getUserMedia", "Errors")}}

## Examples

### Width and height

Here's an example of using `getUserMedia()`, including code to cope with various browsers' prefixes. Note that this is the deprecated way of doing it: See the [Examples](../mediadevices/getusermedia#frame_rate) section under the [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia) for modern examples.

    navigator.getUserMedia = navigator.getUserMedia ||
                             navigator.webkitGetUserMedia ||
                             navigator.mozGetUserMedia;

    if (navigator.getUserMedia) {
       navigator.getUserMedia({ audio: true, video: { width: 1280, height: 720 } },
          function(stream) {
             var video = document.querySelector('video');
             video.srcObject = stream;
             video.onloadedmetadata = function(e) {
               video.play();
             };
          },
          function(err) {
             console.log("The following error occurred: " + err.name);
          }
       );
    } else {
       console.log("getUserMedia not supported");
    }

## Permissions

To use `getUserMedia()` in an installable app (for example, a [Firefox OS app](https://developer.mozilla.org/en-US/docs/Web/Apps/Build/Building_apps_for_Firefox_OS/Firefox_OS_app_beginners_tutorial)), you need to specify one or both of the following fields inside your manifest file:

    "permissions": {
      "audio-capture": {
        "description": "Required to capture audio using getUserMedia()"
      },
      "video-capture": {
        "description": "Required to capture video using getUserMedia()"
      }
    }

See [permission: audio-capture](https://developer.mozilla.org/en-US/docs/Web/Apps/Developing/App_permissions#audio-capture) and [permission: video-capture](https://developer.mozilla.org/en-US/docs/Web/Apps/Developing/App_permissions#video-capture) for more information.

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

`getUserMedia`

53

21

12

79

17

The constraint syntax described here is available as of Firefox 38. Earlier versions (32-37) used an outdated constraint syntax, but the syntax described here is available there through the [adapter.js](https://github.com/webrtc/adapter) polyfill.

No

40

15

12-15

11-12

53

40

53

25

24

The constraint syntax described here is available as of Firefox 38. Earlier versions (32-37) used an outdated constraint syntax, but the syntax described here is available there through the [adapter.js](https://github.com/webrtc/adapter) polyfill.

41

14

12-14

11-12

6.0

1.5

New code should use [`Navigator.mediaDevices.getUserMedia()`](../mediadevices/getusermedia) instead.

## See also

- [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia) that replaces this deprecated method.
- [WebRTC](../webrtc_api) - the introductory page to the API
- [MediaStream API](../media_streams_api) - the API for the media stream objects
- [Taking webcam photos](../webrtc_api/taking_still_photos) - a tutorial on using `getUserMedia() for taking photos rather than video.`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia</a>
