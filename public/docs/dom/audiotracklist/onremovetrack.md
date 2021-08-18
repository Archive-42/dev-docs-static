# AudioTrackList.onremovetrack

The **[`AudioTrackList`](../audiotracklist)** `onremovetrack` event handler is called when the `removetrack` event occurs, indicating that an audio track has been removed from the media element, and therefore also from the `AudioTrackList`.

The event is passed into the event handler in the form of a [`TrackEvent`](../trackevent) object, whose [`track`](../trackevent/track) property identifies the track that was removed from the media element's `AudioTrackList`.

**Note:** You can also add a handler for the `removetrack` event using [`addEventListener()`](../eventtarget/addeventlistener).

## Syntax

    AudioTrackList.onremovetrack = eventHandler;

### Value

Set `onremovetrack` to a function that accepts as input a [`TrackEvent`](../trackevent) object which indicates in its [`track`](../trackevent/track) property which audio track has been removed from the media element.

## Example

This simple example just fetches the current number of audio tracks in the media element whenever a track is removed from the media element.

    document.querySelector("my-video").audioTracks.onremovetrack = function(event) {
      myTrackCount = document.querySelector("my-video").audioTracks.length;
    };

The current number of audio tracks remaining in the media element is obtained from `AudioTrackList` property [`length`](length).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onremovetrack">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList.onremovetrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotracklist-onremovetrack">HTML5<br />
<span class="small">The definition of 'AudioTrackList.onremovetrack' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onremovetrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onremovetrack</a>
