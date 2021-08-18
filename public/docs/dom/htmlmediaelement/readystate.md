# HTMLMediaElement.readyState

The `HTMLMediaElement.readyState` property indicates the readiness state of the media.

## Syntax

    var readyState = audioOrVideo.readyState;

### Value

An `unsigned short`. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>HAVE_NOTHING</code></td><td>0</td><td>No information is available about the media resource.</td></tr><tr class="even"><td><code>HAVE_METADATA</code></td><td>1</td><td>Enough of the media resource has been retrieved that the metadata attributes are initialized. Seeking will no longer raise an exception.</td></tr><tr class="odd"><td><code>HAVE_CURRENT_DATA</code></td><td>2</td><td>Data is available for the current playback position, but not enough to actually play more than one frame.</td></tr><tr class="even"><td><code>HAVE_FUTURE_DATA</code></td><td>3</td><td>Data for the current playback position as well as for at least a little bit of time into the future is available (in other words, at least two frames of video, for example).</td></tr><tr class="odd"><td><code>HAVE_ENOUGH_DATA</code></td><td>4</td><td>Enough data is available—and the download rate is high enough—that the media can be played through to the end without interruption.</td></tr></tbody></table>

## Examples

This example will listen for audio data to be loaded for the element \`example\`. It will then check if at least the current playback position has been loaded. If it has, the audio will play.

    <audio id="example" preload="auto">
     <source src="sound.ogg" type="audio/ogg" />
    </audio>

    var obj = document.getElementById('example');

    obj.addEventListener('loadeddata', function() {

      if(obj.readyState >= 2) {
        obj.play();
      }

    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-readystate">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.readyState' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.readyState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/readyState</a>
