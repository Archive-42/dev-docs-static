TrackEvent()
============

The `TrackEvent()` constructor creates and returns a new [`TrackEvent`](../trackevent) object describing an event which occurred on a list of tracks ([`AudioTrackList`](../audiotracklist), [`VideoTrackList`](../videotracklist), or [`TextTrackList`](../texttracklist)).

Syntax
------

    trackEvent = new TrackEvent(type, eventInfo);

### Parameters

`type`  
The type of track event which is described by the object: `"addtrack"` or `"removetrack"`.

 `eventInfo` <span class="badge inline optional">Optional</span>   
An optional dictionary providing additional information configuring the new event; it can contain the following fields in any combination:

 `track` <span class="badge inline optional">Optional</span>   
The track to which the event refers; this is `null` by default, but should be set to a [`VideoTrack`](../videotrack), [`AudioTrack`](../audiotrack), or [`TextTrack`](../texttrack) as appropriate given the type of track.

 `bubbles` <span class="badge inline optional">Optional</span>   
A Boolean indicating whether the event bubbles or not.

 `cancelable` <span class="badge inline optional">Optional</span>   
A Boolean indicating whether or not the event can be canceled.

 `composed` <span class="badge inline optional">Optional</span>   
A Boolean indicating whether or not the event will trigger listeners outside of a shadow root; see [`Event.composed`](../event/composed) for more details.

### Return value

A newly-created [`TrackEvent`](../trackevent) object, initialized as described by the inputs to the constructor.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-trackevent-trackevent">HTML Living Standard<br />
<span class="small">The definition of 'TrackEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#dom-trackevent-trackevent">HTML5<br />
<span class="small">The definition of 'TrackEvent()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.TrackEvent.TrackEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackEvent/TrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackEvent/TrackEvent</a>
