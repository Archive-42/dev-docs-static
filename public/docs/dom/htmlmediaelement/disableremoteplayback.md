# HTMLMediaElement.disableRemotePlayback

The `HTMLMediaElement.disableRemotePlayback` property determines whether the media element is allowed to have a remote playback UI.

## Syntax

    var remotePlaybackDisabled = element.disableRemotePlayback;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the media element may have a remote playback UI. (false means "not disabled", which means "enabled")

## Example

    var obj = document.createElement('audio');
    obj.disableRemotePlayback = true;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/remote-playback/#the-disableremoteplayback-attribute">Remote Playback API<br />
<span class="small">The definition of 'disableRemotePlayback' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/disableRemotePlayback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/disableRemotePlayback</a>
