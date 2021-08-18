TrackEvent
==========

The `TrackEvent` interface, which is part of the HTML DOM specification, is used for events which represent changes to a set of available tracks on an HTML media element; these events are `addtrack` and `removetrack`. It's important not to confuse `TrackEvent` with the [`RTCTrackEvent`](rtctrackevent) interface, which is used for tracks which are part of an [`RTCPeerConnection`](rtcpeerconnection).

Events based on `TrackEvent` are always sent to one of the media track list types:

-   Events involving video tracks are always sent to the [`VideoTrackList`](videotracklist) found in [`HTMLMediaElement.videoTracks`](htmlmediaelement/videotracks)
-   Events involving audio tracks are always sent to the [`AudioTrackList`](audiotracklist) specified in [`HTMLMediaElement.audioTracks`](htmlmediaelement/audiotracks)
-   Events affecting text tracks are sent to the [`TextTrackList`](texttracklist) object indicated by [`HTMLMediaElement.textTracks`](htmlmediaelement/texttracks).

Constructor
-----------

[`TrackEvent()`](trackevent/trackevent)  
Creates and initializes a new `TrackEvent` object with the event type specified, as well as optional additional properties.

Properties
----------

*`TrackEvent` is based on [`Event`](event), so properties of `Event` are also available on `TrackEvent` objects.*

 [`track`](trackevent/track) <span class="badge inline readonly">Read only </span>   
The DOM track object the event is in reference to. If not `null`, this is always an object of one of the media track types: [`AudioTrack`](audiotrack), [`VideoTrack`](videotrack), or [`TextTrack`](texttrack)).

Methods
-------

*`TrackEvent` has no methods of its own; however, it is based on [`Event`](event), so it provides the methods available on `Event` objects.*

Example
-------

This example sets up a function, `handleTrackEvent()`, which is called for any `addtrack` or `removetrack` event on the first [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element found in the document.

    var videoElem = document.querySelector("video");

    videoElem.videoTracks.addEventListener("addtrack", handleTrackEvent, false);
    videoElem.videoTracks.addEventListener("removetrack", handleTrackEvent, false);
    videoElem.audioTracks.addEventListener("addtrack", handleTrackEvent, false);
    videoElem.audioTracks.addEventListener("removetrack", handleTrackEvent, false);
    videoElem.textTracks.addEventListener("addtrack", handleTrackEvent, false);
    videoElem.textTracks.addEventListener("removetrack", handleTrackEvent, false);

    function handleTrackEvent(event) {
      var trackKind;

      if (event.target instanceof(VideoTrackList)) {
        trackKind = "video";
      } else if (event.target instanceof(AudioTrackList)) {
        trackKind = "audio";
      } else if (event.target instanceof(TextTrackList)) {
        trackKind = "text";
      } else {
        trackKind = "unknown";
      }

      switch(event.type) {
        case "addtrack":
          console.log("Added a " + trackKind + " track");
          break;
        case "removetrack":
          console.log("Removed a " + trackKind + " track");
          break;
      }
    }

The event handler uses the JavaScript `instanceof` operator to determine which type of track the event occurred on, then outputs to console a message indicating what kind of track it is and whether it's being added to or removed from the element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#the-trackevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'TrackEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#trackevent">HTML5<br />
<span class="small">The definition of 'TrackEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrackEvent`

Yes

≤79

?

?

?

Yes

Yes

Yes

?

?

Yes

Yes

`track`

Yes

≤79

?

?

?

Yes

Yes

Yes

?

?

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackEvent</a>
