# AudioTrackList.onchange

The **[`AudioTrackList`](../audiotracklist)** property `onchange` is an event handler which is called when the `change` event occurs, indicating that one or more of the [`AudioTrack`](../audiotrack)s in the `AudioTrackList` have been enabled or disabled.

The event is passed into the event handler in the form of an [`Event`](../event) object; the event doesn't provide any additional information. To determine the new state of media's tracks, you'll have to look at their [`AudioTrack.enabled`](../audiotrack/enabled) flags.

**Note:** You can also add a handler for the `change` event using [`addEventListener()`](../eventtarget/addeventlistener).

## Syntax

    AudioTrackList.onchange = eventHandler;

### Value

Set `onchange` to a function that should be called whenever tracks are enabled or disabled on the media element.

## Example

This snippet establishes a handler for the `change` event that looks at each of the tracks in the list, calling a function to update the state of a user interface control that indicates the current state of the track.

    var trackList = document.querySelector("video").audioTracks;

    trackList.onchange = function(event) {
      trackList.forEach(function(track) {
        updateTrackEnabledButton(track.id, track.enabled);
      });
    };

The `updateTrackEnabledButton()`, in this example, should be a function that finds a user interface control using the track's [`id`](../audiotrack/id) (perhaps the app uses the track ID as the control element's ID) and the track's [`enabled`](../audiotrack/enabled) flag to determine which state the control should be in now.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onchange">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList.onchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotracklist-onchange">HTML5<br />
<span class="small">The definition of 'AudioTrackList.onchange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/onchange</a>
