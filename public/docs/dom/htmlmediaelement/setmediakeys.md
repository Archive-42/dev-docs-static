# HTMLMediaElement.setMediaKeys()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `setMediaKeys()` property of the [`HTMLMediaElement`](../htmlmediaelement) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the passed [`MediaKeys`](../mediakeys), which are those used to decrypt media during playback.

## Syntax

    var Promise = HTMLMediaElement.setMediaKeys(mediaKeys);

### Parameters

mediaKeys  
A reference to a [`MediaKeys`](../mediakeys) object that the [`HTMLMediaElement`](../htmlmediaelement) can use for decryption of media data during playback.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the passed instance of `MediaKeys`.

### Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#dom-htmlmediaelement-setmediakeys">Encrypted Media Extensions<br />
<span class="small">The definition of 'setMediaKeys()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setMediaKeys`

42

13

38

No

29

12.1

42

42

38

29

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setMediaKeys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setMediaKeys</a>
