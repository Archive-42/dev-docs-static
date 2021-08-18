# AudioTrackList.onaddtrack

The **[`AudioTrackList`](../audiotracklist)** property `onaddtrack` is an event handler which is called when the `addtrack` event occurs, indicating that a new audio track has been added to the media element whose audio tracks the `AudioTrackList` represents.

The event is passed into the event handler in the form of a [`TrackEvent`](../trackevent) object, whose [`track`](../trackevent/track) property identifies the newly-added track.

**Note:** You can also add a handler for the `addtrack` event using [`addEventListener()`](../eventtarget/addeventlistener).

## Syntax

    AudioTrackList.onaddtrack = eventHandler;

### Value

Set `onaddtrack` to a function that accepts as input a [`TrackEvent`](../trackevent) object which indicates in its [`track`](../trackevent/track) property which audio track has been added to the media.

## Usage notes

The `addtrack` event is called whenever a new track is added to the media element whose audio tracks are represented by the `AudioTrackList` object. This happens when tracks are added to the element when the media is first attached to the element; one `addtrack` event will occur for each audio track in the media resource.

## Example

This snippet establishes a handler for the `addtrack` event that calls a function, `addToTrackList()`, passing in the [`AudioTrack`](../audiotrack) object representing the newly-added track. In this scenario, that function's role is to add the new track to a list of audio tracks available to choose from.

    document.querySelector("video").audioTracks.onaddtrack = function(event) {
      addToTrackList(event.track);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onaddtrack">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList.onaddtrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotracklist-onaddtrack">HTML5<br />
<span class="small">The definition of 'AudioTrackList.onaddtrack' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onaddtrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onaddtrack</a>
