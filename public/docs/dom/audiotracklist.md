# AudioTrackList

The `AudioTrackList` interface is used to represent a list of the audio tracks contained within a given HTML media element, with each track represented by a separate [`AudioTrack`](audiotrack) object in the list.

Retrieve an instance of this object with [`HTMLMediaElement.audioTracks`](htmlmediaelement/audiotracks). The individual tracks can be accessed using array syntax.

## Properties

_This interface also inherits properties from its parent interface, [`EventTarget`](eventtarget)._

[`length`](audiotracklist/length) <span class="badge inline readonly">Read only </span>  
The number of tracks in the list.

## Event handlers

[`onaddtrack`](audiotracklist/onaddtrack)  
An event handler to be called when the `addtrack` event is fired, indicating that a new audio track has been added to the media element.

[`onchange`](audiotracklist/onchange)  
An event handler to be called when the `change` event occurs. This occurs when one or more tracks have been enabled or disabled by their [`enabled`](audiotrack/enabled) flag being changed.

[`onremovetrack`](audiotracklist/onremovetrack)  
An event handler to call when the `removetrack` event is sent, indicating that an audio track has been removed from the media element.

## Methods

_This interface also inherits methods from its parent interface, [`EventTarget`](eventtarget)._

[`getTrackById()`](audiotracklist/gettrackbyid)  
Returns the [`AudioTrack`](audiotrack) found within the `AudioTrackList` whose [`id`](audiotrack/id) matches the specified string. If no match is found, `null` is returned.

## Events

`addtrack`  
Fired when a new audio track has been added to the media element.  
Also available via the `onaddtrack` property.

`change`  
Fired when a track has been enabled or disabled.  
Also available via the `onchange` property.

`removetrack`  
Fired when a new audio track has been removed from the media element.  
Also available via the `onremovetrack` property.

## Usage notes

In addition to being able to obtain direct access to the audio tracks present on a media element, `AudioTrackList` lets you set event handlers on the `addtrack` and `removetrack` events, so that you can detect when tracks are added to or removed from the media element's stream. See [`onaddtrack`](audiotracklist/onaddtrack) and [`onremovetrack`](audiotracklist/onremovetrack) for details and examples.

## Examples

### Getting a media element's audio track list

To get a media element's [`AudioTrackList`](audiotracklist), use its [`audioTracks`](htmlmediaelement/audiotracks) property.

    var audioTracks = document.querySelector("video").audioTracks;

### Monitoring track count changes

In this example, we have an app that displays information about the number of channels available. To keep it up to date, handlers for the `addtrack` and `removetrack` events are set up.

    audioTracks.onaddtrack = updateTrackCount;
    audioTracks.onremovetrack = updateTrackCount;

    function updateTrackCount(event) {
      trackCount = audioTracks.length;
      drawTrackCountIndicator(trackCount);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#audiotracklist">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#audiotracklist">HTML5<br />
<span class="small">The definition of 'AudioTrackList' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`AudioTrackList`

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

7

No

`addtrack_event`

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

7

No

`change_event`

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

7

No

`getTrackById`

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

7

No

`length`

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

7

No

`onaddtrack`

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

7

No

`onchange`

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

7

No

`onremovetrack`

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

7

No

`removetrack_event`

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

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList</a>
