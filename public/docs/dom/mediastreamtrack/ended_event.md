# MediaStreamTrack: ended event

The `ended` event of the [`MediaStreamTrack`](../mediastreamtrack) interface is fired when playback or streaming has stopped because the end of the media was reached or because no further data is available.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onended"><code>MediaStreamTrack.onended</code></a></td></tr></tbody></table>

## Usage notes

`ended` events fire when the media stream track's source permanently stops sending data on the stream. There are various ways this can happen, including:

- There is no more data left to send.
- The user revoked the permissions needed for the data to be sent.
- The hardware generating the source data has been removed or ejected.
- A remote peer has permanently stopped sending data; pausing media _does not_ generate an `ended` event.

## Examples

This example sets up an event handler for the `ended` event, which changes an on-screen icon to indicate that the track is no longer active.

    track.addEventListener('ended', () => {
      let statusElem = document.getElementById("status-icon");
      statusElem.src = "/images/stopped-icon.png";
    })

You can also set up the event handler using the [`MediaStreamTrack.onended`](onended) property:

    track.onended = function() {
      let statusElem = document.getElementById("status-icon");

      statusElem.src = "/images/stopped-icon.png";
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastreamtrack-ended">Media Capture and Streams<br />
<span class="small">The definition of 'ended' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ended_event`

Yes

12

50

No

Yes

Yes

Yes

Yes

50

Yes

Yes

Yes

## See also

- [`HTMLMediaElement: playing event`](../htmlmediaelement/playing_event)
- [`HTMLMediaElement: waiting event`](../htmlmediaelement/waiting_event)
- [`HTMLMediaElement: seeking event`](../htmlmediaelement/seeking_event)
- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
- [`HTMLMediaElement: ended event`](../htmlmediaelement/ended_event)
- [`AudioScheduledSourceNode: ended event`](../audioscheduledsourcenode/ended_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/ended_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/ended_event</a>
