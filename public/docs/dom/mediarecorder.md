MediaRecorder
=============

The `MediaRecorder` interface of the [MediaStream Recording API](mediastream_recording_api) provides functionality to easily record media. It is created using the [`MediaRecorder()`](mediarecorder/mediarecorder) constructor.

Constructor
-----------

[`MediaRecorder()`](mediarecorder/mediarecorder)  
Creates a new `MediaRecorder` object, given a [`MediaStream`](mediastream) to record. Options are available to do things like set the container's MIME type (such as `"video/webm"` or `"video/mp4"`) and the bit rates of the audio and video tracks or a single overall bit rate.

Properties
----------

 [`MediaRecorder.mimeType`](mediarecorder/mimetype) <span class="badge inline readonly">Read only </span>   
Returns the MIME type that was selected as the recording container for the `MediaRecorder` object when it was created.

 [`MediaRecorder.state`](mediarecorder/state) <span class="badge inline readonly">Read only </span>   
Returns the current state of the `MediaRecorder` object (`inactive`, `recording`, or `paused`.)

 [`MediaRecorder.stream`](mediarecorder/stream) <span class="badge inline readonly">Read only </span>   
Returns the stream that was passed into the constructor when the `MediaRecorder` was created.

[`MediaRecorder.ignoreMutedMedia`](mediarecorder/ignoremutedmedia)  
Indicates whether the `MediaRecorder` instance will record input when the input [`MediaStreamTrack`](mediastreamtrack) is muted. If this attribute is `false`, `MediaRecorder` will record silence for audio and black frames for video. The default is `false`.

 [`MediaRecorder.videoBitsPerSecond`](mediarecorder/videobitspersecond) <span class="badge inline readonly">Read only </span>   
Returns the video encoding bit rate in use. This may differ from the bit rate specified in the constructor (if it was provided).

 [`MediaRecorder.audioBitsPerSecond`](mediarecorder/audiobitspersecond) <span class="badge inline readonly">Read only </span>   
Returns the audio encoding bit rate in use. This may differ from the bit rate specified in the constructor (if it was provided).

Methods
-------

[`MediaRecorder.pause()`](mediarecorder/pause)  
Pauses the recording of media.

[`MediaRecorder.requestData()`](mediarecorder/requestdata)  
Requests a [`Blob`](blob) containing the saved data received thus far (or since the last time `requestData()` was called. After calling this method, recording continues, but in a new `Blob`.

[`MediaRecorder.resume()`](mediarecorder/resume)  
Resumes recording of media after having been paused.

[`MediaRecorder.start()`](mediarecorder/start)  
Begins recording media; this method can optionally be passed a `timeslice` argument with a value in milliseconds. If this is specified, the media will be captured in separate chunks of that duration, rather than the default behavior of recording the media in a single large chunk.

[`MediaRecorder.stop()`](mediarecorder/stop)  
Stops recording, at which point a `dataavailable` event containing the final `Blob` of saved data is fired. No more recording occurs.

Static methods
--------------

[`MediaRecorder.isTypeSupported()`](mediarecorder/istypesupported)  
A static method which returns a `true` or `false` value indicating if the given MIME media type is supported by the current user agent.

Event handlers
--------------

[`MediaRecorder.ondataavailable`](mediarecorder/ondataavailable)  
Called to handle the `dataavailable` event, which is periodically triggered each time `timeslice` milliseconds of media have been recorded (or when the entire media has been recorded, if `timeslice` wasn't specified). The event, of type [`BlobEvent`](blobevent), contains the recorded media in its [`data`](blobevent/data) property. You can then collect and act upon that recorded media data using this event handler.

[`MediaRecorder.onerror`](mediarecorder/onerror)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `error` event, including reporting errors that arise with media recording. These are fatal errors that stop recording. The received event is based on the [`MediaRecorderErrorEvent`](mediarecordererrorevent) interface, whose [`error`](mediarecordererrorevent/error) property contains a [`DOMException`](domexception) that describes the actual error that occurred.

[`MediaRecorder.onpause`](mediarecorder/onpause)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `pause` event, which occurs when media recording is paused.

[`MediaRecorder.onresume`](mediarecorder/onresume)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `resume` event, which occurs when media recording resumes after being paused.

[`MediaRecorder.onstart`](mediarecorder/onstart)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `start` event, which occurs when media recording starts.

[`MediaRecorder.onstop`](mediarecorder/onstop)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `stop` event, which occurs when media recording ends, either when the [`MediaStream`](mediastream) ends — or after the [`MediaRecorder.stop()`](mediarecorder/stop) method is called.

 [`MediaRecorder.onwarning`](mediarecorder/onwarning) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called to handle the `warning` event, which occurs when media recording has a non-fatal error, or after the [`MediaRecorder.onwarning()`](mediarecorder/onwarning) method is called.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`error`  
Fired when an error occurs: for example because recording wasn't allowed or was attempted using an unsupported codec.  
Also available via the `onerror` property.

 `warning`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Fired when a problem occurs that does not halt recording.  
Also available via the `onwarning` property.

Example
-------

    if (navigator.mediaDevices) {
      console.log('getUserMedia supported.');

      var constraints = { audio: true };
      var chunks = [];

      navigator.mediaDevices.getUserMedia(constraints)
      .then(function(stream) {

        var mediaRecorder = new MediaRecorder(stream);

        visualize(stream);

        record.onclick = function() {
          mediaRecorder.start();
          console.log(mediaRecorder.state);
          console.log("recorder started");
          record.style.background = "red";
          record.style.color = "black";
        }

        stop.onclick = function() {
          mediaRecorder.stop();
          console.log(mediaRecorder.state);
          console.log("recorder stopped");
          record.style.background = "";
          record.style.color = "";
        }

        mediaRecorder.onstop = function(e) {
          console.log("data available after MediaRecorder.stop() called.");

          var clipName = prompt('Enter a name for your sound clip');

          var clipContainer = document.createElement('article');
          var clipLabel = document.createElement('p');
          var audio = document.createElement('audio');
          var deleteButton = document.createElement('button');

          clipContainer.classList.add('clip');
          audio.setAttribute('controls', '');
          deleteButton.innerHTML = "Delete";
          clipLabel.innerHTML = clipName;

          clipContainer.appendChild(audio);
          clipContainer.appendChild(clipLabel);
          clipContainer.appendChild(deleteButton);
          soundClips.appendChild(clipContainer);

          audio.controls = true;
          var blob = new Blob(chunks, { 'type' : 'audio/ogg; codecs=opus' });
          chunks = [];
          var audioURL = URL.createObjectURL(blob);
          audio.src = audioURL;
          console.log("recorder stopped");

          deleteButton.onclick = function(e) {
            evtTgt = e.target;
            evtTgt.parentNode.parentNode.removeChild(evtTgt.parentNode);
          }
        }

        mediaRecorder.ondataavailable = function(e) {
          chunks.push(e.data);
        }
      })
      .catch(function(err) {
        console.log('The following error occurred: ' + err);
      })
    }

This code sample is inspired by the Web Dictaphone demo. Some lines have been omitted for brevity; [refer to the source](https://github.com/mdn/web-dictaphone/) for the complete code.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#mediarecorder-api">MediaStream Recording</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaRecorder`

47

79

25

Prior to Firefox 58, using `MediaStream.addTrack()` on a stream obtained using `getUserMedia()`, then attempting to record the resulting stream would result in only recording the original stream without the added tracks (severe bug).

No

36

14

47

47

25

Prior to Firefox 58, using `MediaStream.addTrack()` on a stream obtained using `getUserMedia()`, then attempting to record the resulting stream would result in only recording the original stream without the added tracks (severe bug).

36

14

5.0

`MediaRecorder`

47

79

25

No

36

14

47

47

25

36

14

5.0

`audioBitsPerSecond`

49

79

71

No

36

14.1

49

49

79

36

14.5

5.0

`error_event`

49

79

25

No

36

14

49

49

25

36

14

5.0

`ignoreMutedMedia`

49-57

No

No

No

36-44

No

49-57

49-57

No

36-44

No

5.0-7.0

`isTypeSupported`

47

79

25

No

36

14

47

47

25

36

14

5.0

`mimeType`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

Starting with Firefox 71, the behavior of `mimeType` is more consistent. For example, it now returns the media type even after recording has stopped.

No

36

14

49

47-49

Prior to Chrome 49, only video is supported, not audio.

49

47-49

Prior to Chrome 49, only video is supported, not audio.

25

36

14

5.0

`ondataavailable`

49

79

25

No

36

14

49

49

25

36

14

5.0

`onerror`

49

79

25

No

36

14

49

49

25

36

14

5.0

`onpause`

49

79

65

No

36

14.1

49

49

65

36

14.5

5.0

`onresume`

49

79

65

No

36

14.1

49

49

65

36

14.5

5.0

`onstart`

49

79

25

No

36

14

49

49

25

36

14

5.0

`onstop`

49

79

25

No

36

14

49

49

25

36

14

5.0

`onwarning`

49

79

25-71

No

36

No

49

49

25

36

No

5.0

`pause`

49

79

25

No

36

14.1

49

49

25

36

14.5

5.0

`requestData`

49

79

25

No

36

14

49

49

25

36

14

5.0

`resume`

49

79

25

No

36

14.1

49

49

25

36

14.5

5.0

`start`

47

79

25

No

36

14

47

47

25

36

14

5.0

`state`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

No

36

14

49

47-49

Prior to Chrome 49, only video is supported, not audio.

49

47-49

Prior to Chrome 49, only video is supported, not audio.

25

36

14

5.0

`stop`

49

79

25

No

36

14

49

49

25

36

14

5.0

`stream`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

No

36

14

49

49

47-49

Prior to Chrome 49, only video is supported, not audio.

25

36

14

5.0

`videoBitsPerSecond`

49

79

71

No

36

14.1

49

49

79

36

14.5

5.0

`warning_event`

49

79

25-71

No

36

No

49

49

25

36

No

5.0

See also
--------

-   [Using the MediaRecorder API](mediastream_recording_api/using_the_mediastream_recording_api)
-   [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
-   [Recording a media element](mediastream_recording_api/recording_a_media_element)
-   [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
-   [`MediaDevices.getUserMedia`](mediadevices/getusermedia)
-   [OpenLang](https://github.com/chrisjohndigital/OpenLang): HTML5 video language lab web application using MediaDevices and the MediaStream Recording API for video recording ([source on GitHub](https://github.com/chrisjohndigital/OpenLang))

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder</a>
