# AudioTrackList.getTrackById()

The **[`AudioTrackList`](../audiotracklist)** method `getTrackById()` returns the first [`AudioTrack`](../audiotrack) object from the track list whose [`id`](../audiotrack/id) matches the specified string. This lets you find a specified track if you know its ID string.

## Syntax

    var theTrack = AudioTrackList.getTrackById(id);

### Parameters

`id`  
A [`DOMString`](../domstring) indicating the ID of the track to locate within the track list.

### Return value

An [`AudioTrack`](../audiotrack) object indicating the first track found within the `AudioTrackList` whose `id` matches the specified string. If no match is found, this method returns `null`.

The tracks are searched in their natural order; that is, in the order defined by the media resource itself, or, if the resource doesn't define an order, the relative order in which the tracks are declared by the media resource.

## Example

This example suggests a hypothetical game in which movies are used as cut-scenes or other key set pieces within the game. Each movie has one audio track for each character, as well as one for the music, sound effects, and so forth. This function allows the game to disable a specific character's audio in order to adjust the movie's performance based on occurrences within the game; if the character's dialog isn't relevant, it gets left out. Obviously that would require some clever graphic design to make work, but... it's a hypothetical game.

    function disableCharacter(videoElem, characterName) {
      videoElem.audioTracks.getTrackById(characterName).enabled = false;
    }

This short function gets the [`AudioTrackList`](../audiotracklist) containing the video's audio tracks using [`HTMLMediaElement.audioTracks`](../htmlmediaelement/audiotracks), then calls `getTrackById()` on it, specifying the character's name. The resulting track's audio is then disabled by setting its [`enabled`](../audiotrack/enabled) flag to `false`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-audiotracklist-gettrackbyid">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList.getTrackById()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotracklist-getTrackById">HTML5<br />
<span class="small">The definition of 'AudioTrackList.getTrackById()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/getTrackById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/getTrackById</a>
