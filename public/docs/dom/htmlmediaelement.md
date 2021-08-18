# HTMLMediaElement

The `HTMLMediaElement` interface adds to [`HTMLElement`](htmlelement) the properties and methods needed to support basic media-related capabilities that are common to audio and video. The [`HTMLVideoElement`](htmlvideoelement) and [`HTMLAudioElement`](htmlaudioelement) elements both inherit this interface.

## Properties

_This interface also inherits properties from its ancestors [`HTMLElement`](htmlelement), [`Element`](element), [`Node`](node), and [`EventTarget`](eventtarget)._

[`HTMLMediaElement.audioTracks`](htmlmediaelement/audiotracks)  
A [`AudioTrackList`](audiotracklist) that lists the [`AudioTrack`](audiotrack) objects contained in the element.

[`HTMLMediaElement.autoplay`](htmlmediaelement/autoplay)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`autoplay`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-autoplay) HTML attribute, indicating whether playback should automatically begin as soon as enough media is available to do so without interruption.

**Note**: Automatically playing audio when the user doesn't expect or desire it is a poor user experience and should be avoided in most cases, though there are exceptions. See the [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide) for more information. Keep in mind that browsers may ignore autoplay requests, so you should ensure that your code isn't dependent on autoplay working.

[`HTMLMediaElement.buffered`](htmlmediaelement/buffered) <span class="badge inline readonly">Read only </span>  
Returns a [`TimeRanges`](timeranges) object that indicates the ranges of the media source that the browser has buffered (if any) at the moment the `buffered` property is accessed.

[`HTMLMediaElement.controller`](htmlmediaelement/controller)  
Is a <span class="page-not-created">`MediaController`</span> object that represents the media controller assigned to the element, or `null` if none is assigned.

[`HTMLMediaElement.controls`](htmlmediaelement/controls)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`controls`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-controls) HTML attribute, indicating whether user interface items for controlling the resource should be displayed.

[`HTMLMediaElement.controlsList`](htmlmediaelement/controlslist) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMTokenList`](domtokenlist) that helps the user agent select what controls to show on the media element whenever the user agent shows its own set of controls. The `DOMTokenList` takes one or more of three possible values: `nodownload`, `nofullscreen`, and `noremoteplayback`.

[`HTMLMediaElement.crossOrigin`](htmlmediaelement/crossorigin)  
A [`DOMString`](domstring) indicating the [CORS setting](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for this media element.

[`HTMLMediaElement.currentSrc`](htmlmediaelement/currentsrc) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) with the absolute URL of the chosen media resource.

[`HTMLMediaElement.currentTime`](htmlmediaelement/currenttime)  
A double-precision floating-point value indicating the current playback time in seconds; if the media has not started to play and has not been seeked, this value is the media's initial playback time. Setting this value seeks the media to the new time. The time is specified relative to the media's timeline.

[`HTMLMediaElement.defaultMuted`](htmlmediaelement/defaultmuted)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`muted`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-muted) HTML attribute, which indicates whether the media element's audio output should be muted by default.

[`HTMLMediaElement.defaultPlaybackRate`](htmlmediaelement/defaultplaybackrate)  
A `double` indicating the default playback rate for the media.

[`HTMLMediaElement.disableRemotePlayback`](htmlmediaelement/disableremoteplayback)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that sets or returns the remote playback state, indicating whether the media element is allowed to have a remote playback UI.

[`HTMLMediaElement.duration`](htmlmediaelement/duration) <span class="badge inline readonly">Read only </span>  
A read-only double-precision floating-point value indicating the total duration of the media in seconds. If no media data is available, the returned value is `NaN`. If the media is of indefinite length (such as streamed live media, a WebRTC call's media, or similar), the value is `+Infinity`.

[`HTMLMediaElement.ended`](htmlmediaelement/ended) <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media element has finished playing.

[`HTMLMediaElement.error`](htmlmediaelement/error) <span class="badge inline readonly">Read only </span>  
Returns a [`MediaError`](mediaerror) object for the most recent error, or `null` if there has not been an error.

[`HTMLMediaElement.loop`](htmlmediaelement/loop)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`loop`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-loop) HTML attribute, which indicates whether the media element should start over when it reaches the end.

[`HTMLMediaElement.mediaGroup`](htmlmediaelement/mediagroup)  
A [`DOMString`](domstring) that reflects the [`mediagroup`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-mediagroup) HTML attribute, which indicates the name of the group of elements it belongs to. A group of media elements shares a common <span class="page-not-created">`MediaController`</span>.

<span class="page-not-created">`HTMLMediaElement.mediaKeys`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`MediaKeys`](mediakeys) object or `null`. MediaKeys is a set of keys that an associated HTMLMediaElement can use for decryption of media data during playback.

[`HTMLMediaElement.muted`](htmlmediaelement/muted)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that determines whether audio is muted. `true` if the audio is muted and `false` otherwise.

[`HTMLMediaElement.networkState`](htmlmediaelement/networkstate) <span class="badge inline readonly">Read only </span>  
Returns a `unsigned short` (enumeration) indicating the current state of fetching the media over the network.

[`HTMLMediaElement.paused`](htmlmediaelement/paused) <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media element is paused.

[`HTMLMediaElement.playbackRate`](htmlmediaelement/playbackrate)  
Is a `double` that indicates the rate at which the media is being played back.

<span class="page-not-created">`HTMLMediaElement.played`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`TimeRanges`](timeranges) object that contains the ranges of the media source that the browser has played, if any.

<span class="page-not-created">`HTMLMediaElement.preload`</span>  
Is a [`DOMString`](domstring) that reflects the [`preload`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-preload) HTML attribute, indicating what data should be preloaded, if any. Possible values are: `none`, `metadata`, `auto`.

<span class="page-not-created">`HTMLMediaElement.preservesPitch`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that determines if the pitch of the sound will be preserved. If set to `false`, the pitch will adjust to the speed of the audio. This is implemented with prefixes in Firefox (`mozPreservesPitch`) and WebKit (`webkitPreservesPitch`).

[`HTMLMediaElement.readyState`](htmlmediaelement/readystate) <span class="badge inline readonly">Read only </span>  
Returns a `unsigned short` (enumeration) indicating the readiness state of the media.

[`HTMLMediaElement.seekable`](htmlmediaelement/seekable) <span class="badge inline readonly">Read only </span>  
Returns a [`TimeRanges`](timeranges) object that contains the time ranges that the user is able to seek to, if any.

<span class="page-not-created">`HTMLMediaElement.seeking`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media is in the process of seeking to a new position.

[`HTMLMediaElement.sinkId`](htmlmediaelement/sinkid) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`DOMString`](domstring) that is the unique ID of the audio device delivering output, or an empty string if it is using the user agent default. This ID should be one of the `MediaDeviceInfo.deviceid` values returned from [`MediaDevices.enumerateDevices()`](mediadevices/enumeratedevices), `id-multimedia`, or `id-communications`.

[`HTMLMediaElement.src`](htmlmediaelement/src)  
Is a [`DOMString`](domstring) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) HTML attribute, which contains the URL of a media resource to use.

[`HTMLMediaElement.srcObject`](htmlmediaelement/srcobject)  
Is a [`MediaStream`](mediastream) representing the media to play or that has played in the current `HTMLMediaElement`, or `null` if not assigned.

[`HTMLMediaElement.textTracks`](htmlmediaelement/texttracks) <span class="badge inline readonly">Read only </span>  
Returns the list of [`TextTrack`](texttrack) objects contained in the element.

[`HTMLMediaElement.videoTracks`](htmlmediaelement/videotracks) <span class="badge inline readonly">Read only </span>  
Returns the list of [`VideoTrack`](videotrack) objects contained in the element.

[`HTMLMediaElement.volume`](htmlmediaelement/volume)  
Is a `double` indicating the audio volume, from 0.0 (silent) to 1.0 (loudest).

### Event handlers

[`HTMLMediaElement.onencrypted`](htmlmediaelement/onencrypted)  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when the media is encrypted.

[`HTMLMediaElement.onwaitingforkey`](htmlmediaelement/onwaitingforkey)  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when playback is blocked while waiting for an encryption key.

## Obsolete attributes

These attributes are obsolete and should not be used, even if a browser still supports them.

<span class="page-not-created">`HTMLMediaElement.mozAudioCaptured`</span> <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Related to audio stream capture.

<span class="page-not-created">`HTMLMediaElement.mozChannels`</span> <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a `double` representing the number of channels in the audio resource (e.g., `2` for stereo).

<span class="page-not-created">`HTMLMediaElement.mozFragmentEnd`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a `double` that provides access to the fragment end time if the media element has a fragment URI for `currentSrc`, otherwise it is equal to the media duration.

<span class="page-not-created">`HTMLMediaElement.mozFrameBufferLength`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a `unsigned long` that indicates the number of samples that will be returned in the framebuffer of each `MozAudioAvailable` event. This number is a total for all channels, and by default is set to be the number of channels \* 1024 (e.g., 2 channels \* 1024 samples = 2048 total).

The `mozFrameBufferLength` property can be set to a new value for lower latency, larger amounts of data, etc. The size given _must_ be a number between 512 and 16384. Using any other size results in an exception being thrown. The best time to set a new length is after the [loadedmetadata](htmlmediaelement/loadedmetadata_event) event fires, when the audio info is known, but before the audio has started or `MozAudioAvailable` events have begun firing.

<span class="page-not-created">`HTMLMediaElement.mozSampleRate`</span> <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a `double` representing the number of samples per second that will be played. For example, 44100 samples per second is the sample rate used by CD audio.

### Obsolete event handlers

<span class="page-not-created">`HTMLMediaElement.onmozinterruptbegin`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when the media element is interrupted because of the Audio Channel manager. This was Firefox-specific, having been implemented for Firefox OS, and was removed in Firefox 55.

<span class="page-not-created">`HTMLMediaElement.onmozinterruptend`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when the interruption is concluded. This was Firefox-specific, having been implemented for Firefox OS, and was removed in Firefox 55.

## Methods

_This interface also inherits methods from its ancestors [`HTMLElement`](htmlelement), [`Element`](element), [`Node`](node), and [`EventTarget`](eventtarget)._

<span class="page-not-created">`HTMLMediaElement.addTextTrack()`</span>  
Adds a text track (such as a track for subtitles) to a media element.

[`HTMLMediaElement.captureStream()`](htmlmediaelement/capturestream) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns [`MediaStream`](mediastream), captures a stream of the media content.

[`HTMLMediaElement.canPlayType()`](htmlmediaelement/canplaytype)  
Given a string specifying a MIME media type (potentially with the [`codecs` parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter) included), `canPlayType()` returns the string `probably` if the media should be playable, `maybe` if there's not enough information to determine whether the media will play or not, or an empty string if the media cannot be played.

[`HTMLMediaElement.fastSeek()`](htmlmediaelement/fastseek) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Quickly seeks to the given time with low precision.

[`HTMLMediaElement.load()`](htmlmediaelement/load)  
Resets the media to the beginning and selects the best available source from the sources provided using the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) attribute or the [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element.

[`HTMLMediaElement.pause()`](htmlmediaelement/pause)  
Pauses the media playback.

[`HTMLMediaElement.play()`](htmlmediaelement/play)  
Begins playback of the media.

[`HTMLMediaElement.seekToNextFrame()`](htmlmediaelement/seektonextframe) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Seeks to the next frame in the media. This non-standard, experimental method makes it possible to manually drive reading and rendering of media at a custom speed, or to move through the media frame-by-frame to perform filtering or other operations.

[`HTMLMediaElement.setMediaKeys()`](htmlmediaelement/setmediakeys) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). Sets the [`MediaKeys`](mediakeys) keys to use when decrypting media during playback.

[`HTMLMediaElement.setSinkId()`](htmlmediaelement/setsinkid) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Sets the ID of the audio device to use for output and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). This only works when the application is authorized to use the specified device.

## Obsolete methods

_These methods are obsolete and should not be used, even if a browser still supports them._

<span class="page-not-created">`HTMLMediaElement.mozCaptureStream()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
\[enter description\]

<span class="page-not-created">`HTMLMediaElement.mozCaptureStreamUntilEnded()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
\[enter description\]

<span class="page-not-created">`HTMLMediaElement.mozGetMetadata()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), which contains properties that represent metadata from the playing media resource as `{key: value}` pairs. A separate copy of the data is returned each time the method is called. This method must be called after the [loadedmetadata](htmlmediaelement/loadedmetadata_event) event fires.

<span class="page-not-created">`HTMLMediaElement.mozLoadFrom()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This method, available only in Mozilla's implementation, loads data from another media element. This works similarly to `load()` except that instead of running the normal resource selection algorithm, the source is set to the `other` element's `currentSrc`. This is optimized so this element gets access to all of the `other` element's cached and buffered data; in fact, the two elements share downloaded data, so data downloaded by either element is available to both.

## Events

_Inherits methods from its parent, [`HTMLElement`](htmlelement)_ , defined in the [`GlobalEventHandlers`](globaleventhandlers) mixin. Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`abort`](htmlmediaelement/abort_event)  
Fired when the resource was not fully loaded, but not as the result of an error.

[`canplay`](htmlmediaelement/canplay_event)  
Fired when the user agent can play the media, but estimates that **not** enough data has been loaded to play the media up to its end without having to stop for further buffering of content

[`canplaythrough`](htmlmediaelement/canplaythrough_event)  
Fired when the user agent can play the media, and estimates that enough data has been loaded to play the media up to its end without having to stop for further buffering of content.

[`durationchange`](htmlmediaelement/durationchange_event)  
Fired when the duration attribute has been updated.

[`emptied`](htmlmediaelement/emptied_event)  
Fired when the media has become empty; for example, when the media has already been loaded (or partially loaded), and the [`HTMLMediaElement.load()`](htmlmediaelement/load) method is called to reload it.

[`ended`](htmlmediaelement/ended_event)  
Fired when playback stops when end of the media (&lt;audio&gt; or &lt;video&gt;) is reached or because no further data is available.

[`error`](htmlmediaelement/error_event)  
Fired when the resource could not be loaded due to an error.

[`loadeddata`](htmlmediaelement/loadeddata_event)  
Fired when the first frame of the media has finished loading.

[`loadedmetadata`](htmlmediaelement/loadedmetadata_event)  
Fired when the metadata has been loaded

[`loadstart`](htmlmediaelement/loadstart_event)  
Fired when the browser has started to load a resource.

[`pause`](htmlmediaelement/pause_event)  
Fired when a request to pause play is handled and the activity has entered its paused state, most commonly occurring when the media's [`HTMLMediaElement.pause()`](htmlmediaelement/pause) method is called.

[`play`](htmlmediaelement/play_event)  
Fired when the `paused` property is changed from `true` to `false`, as a result of the [`HTMLMediaElement.play()`](htmlmediaelement/play) method, or the `autoplay` attribute

[`playing`](htmlmediaelement/playing_event)  
Fired when playback is ready to start after having been paused or delayed due to lack of data

[`progress`](htmlmediaelement/progress_event)  
Fired periodically as the browser loads a resource.

[`ratechange`](htmlmediaelement/ratechange_event)  
Fired when the playback rate has changed.

[`seeked `](htmlmediaelement/seeked_event)  
Fired when a seek operation completes

[`seeking`](htmlmediaelement/seeking_event)  
Fired when a seek operation begins

[`stalled`](htmlmediaelement/stalled_event)  
Fired when the user agent is trying to fetch media data, but data is unexpectedly not forthcoming.

[`suspend`](htmlmediaelement/suspend_event)  
Fired when the media data loading has been suspended.

[`timeupdate`](htmlmediaelement/timeupdate_event)  
Fired when the time indicated by the [`currentTime`](htmlmediaelement/currenttime) attribute has been updated.

[`volumechange`](htmlmediaelement/volumechange_event)  
Fired when the volume has changed.

[`waiting`](htmlmediaelement/waiting_event)  
Fired when playback has stopped because of a temporary lack of data.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#introduction">Encrypted Media Extensions<br />
<span class="small">The definition of 'Encrypted Media Extensions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <a href="mediakeys"><code>MediaKeys</code></a>, <span class="page-not-created"><code>MediaEncryptedEvent</code></span>, <span class="page-not-created"><code>setMediaKeys</code></span>, <span class="page-not-created"><code>onencrypted</code></span>, and <span class="page-not-created"><code>onwaitingforkey</code></span>.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/the-video-element.html#htmlmediaelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLMediaElement`

1

12

3.5

5.5

10.5

1.3

1

18

4

11

1

1.0

`abort_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

`addTextTrack`

23

26

12

31

11

≤12.1

6

≤37

≤37

25

26

31

≤12.1

6

1.5

1.5

`audioTracks`

37

79

12-79

33

10

24

6.1

No

37

33

24

6.1

No

`autoplay`

1

12

3.5

9

≤12.1

3.2

1

18

4

≤12.1

3

1.0

`buffered`

43

12

4

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`canplay_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`canplaythrough_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`canPlayType`

3

12

3.5

Prior to Firefox 28, `canPlayType()` returned `probably` when asked about WebM audio or video files without the `codecs` parameter. Since multiple codecs are supported, this is not enough information to determine if a file can be played, so `maybe` is now correctly returned.

9

≤12.1

4

≤37

18

4

≤12.1

3

1.0

`captureStream`

62

79

15

No

49

No

62

62

15

46

No

8.0

`controller`

No

No

No

Firefox doesn't implement this yet. See [bug 847377](https://bugzil.la/847377).

No

No

6

No

No

No

Firefox doesn't implement this yet. See [bug 847377](https://bugzil.la/847377).

No

6

No

`controls`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`controlsList`

58

≤79

No

No

45

No

58

58

No

43

No

7.0

`crossOrigin`

33

13

22

12-22

No

20

10

4.4.3

33

22

14-22

20

10

2.0

`currentSrc`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`currentTime`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`defaultMuted`

15

12

11

No

≤12.1

6

≤37

18

14

≤12.1

6

1.0

`defaultPlaybackRate`

43

12

20

9

≤12.1

3.1

43

43

20

≤12.1

2

4.0

`disableRemotePlayback`

49

79

No

No

36

13.1

No

See [bug 521319](https://crbug.com/521319)

49

No

36

13

5.0

`duration`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`durationchange_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`emptied_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`ended`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`ended_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`error`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

`error_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

`fastSeek`

No

No

31

No

No

6.1

No

?

31

No

6.1

?

`getStartDate`

No

No

No

No

No

9

No

No

No

No

9

No

`initialTime`

?

?

9-23

9

?

6-6.1

?

?

9-23

?

6-7

?

`load`

1

12

3.5

9

≤12.1

3.2

1

18

4

≤12.1

3

1.0

`loadeddata_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`loadedmetadata_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`loadstart_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

`loop`

3

12

11

9

≤12.1

4

≤37

18

14

≤12.1

3

1.0

`mediaGroup`

No

No

No

Firefox doesn't implement this yet. See [bug 847377](https://bugzil.la/847377).

No

?

6

No

No

No

Firefox doesn't implement this yet. See [bug 847377](https://bugzil.la/847377).

?

6

No

`mediaKeys`

42

13

38

No

29

12.1

42

42

38

29

12.2

4.0

`mozAudioCaptured`

No

No

15

No

No

No

No

No

15

?

No

No

`mozCaptureStreamUntilEnded`

No

No

15

No

No

No

No

No

15

?

No

No

`mozChannels`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

`mozFragmentEnd`

No

No

9

No

No

No

No

No

9

?

No

No

`mozFrameBufferLength`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

`mozGetMetadata`

No

No

17

No

No

No

No

No

17

No

No

No

`mozLoadFrom`

No

No

3.6-24

No

No

No

No

No

4-24

No

No

No

`mozSampleRate`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

`muted`

43

12

3.5

9

≤12.1

3.2

Yes

Yes

4

≤12.1

3

Yes

`networkState`

43

12

3.5

The `NETWORK_LOADED` state was removed to align with the HTML spec in Firefox 4.

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

`onencrypted`

42

13

38

No

29

12.1

42

42

38

29

12.2

4.0

`onerror`

Yes

12

3.5

9

Yes

1.3

Yes

Yes

4

Yes

1

Yes

`onmozinterruptbegin`

No

No

Yes-55

No

No

No

No

No

Yes-55

?

No

No

`onmozinterruptend`

No

No

Yes-55

No

No

No

No

No

Yes-55

?

No

No

`onwaitingforkey`

55

79

52

No

42

12.1

55

55

52

42

12.2

6.0

`pause`

Yes

12

3.5

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

`pause_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`paused`

43

12

3.5

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

`play`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

`play_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`playbackRate`

43

12

20

9

≤12.1

3.1

Yes

Yes

20

≤12.1

2

Yes

`played`

43

12

15

9

≤12.1

3.1

Yes

Yes

15

≤12.1

2

Yes

`playing_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`preload`

5

12

4

9

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`preservesPitch`

86

86

20

See [bug 1652950](https://bugzil.la/1652950)

No

72

4

See [bug 214922](https://webkit.org/b/214922)

86

86

20

See [bug 1652950](https://bugzil.la/1652950)

No

4

See [bug 214922](https://webkit.org/b/214922)

14.0

`progress_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

`ratechange_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`readyState`

43

12

3.5

5.5

≤12.1

3.1

43

43

4

≤12.1

2

4.0

`remote`

56

79

No

No

43

13.1

No

See [bug 521319](https://crbug.com/521319)

56

No

43

13.4

6.0

`seekable`

43

12

8

9

≤12.1

3.1

Yes

Yes

8

≤12.1

2

Yes

`seeked_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`seeking`

43

12

3.5

9

≤12.1

3.2

Yes

Yes

4

≤12.1

2

Yes

`seeking_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`seekToNextFrame`

No

No

56

No

?

No

No

?

56

?

No

?

`setMediaKeys`

42

13

38

No

29

12.1

42

42

38

29

12.2

4.0

`setSinkId`

49

17

64

No

36

No

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

64

36

No

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

`sinkId`

49

17

No

No

36

No

No

49

No

?

No

5.0

`src`

43

12

3.5

9

≤12.1

3.2

Yes

Yes

4

≤12.1

2

Yes

`srcObject`

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

12

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

42

Only supports `MediaStream` objects (see [bug 886194](https://bugzil.la/886194)).

18-58

No

39

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

11

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273).

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

42

Only supports `MediaStream` objects (see [bug 886194](https://bugzil.la/886194)).

18-58

41

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

11

6.0

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

`stalled_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`suspend_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`textTracks`

23

12

31

10

≤12.1

6

≤37

25

31

≤12.1

6

1.0

`timeupdate_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

`videoTracks`

37

79

12-79

33

No

24

6.1

No

37

33

24

6.1

No

`volume`

43

12

3.5

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

`volumechange_event`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`waiting_event`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

## See also

### References

- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) HTML elements.
- [`HTMLVideoElement`](htmlvideoelement) and [`HTMLAudioElement`](htmlaudioelement) interfaces, derived from `HTMLMediaElement`.

### Guides

- [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
- Learning area: [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
- [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
- [Handling media support issues in web content](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Support_issues)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement</a>
