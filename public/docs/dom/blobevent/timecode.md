# BlobEvent.timecode

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `timecode` readonlyinline property of the [`BlobEvent`](../blobevent) interface a [`DOMHighResTimeStamp`](../domhighrestimestamp) indicating the difference between the timestamp of the first chunk in data, and the timestamp of the first chunk in the first BlobEvent produced by this recorder. Note that the timecode in the first produced BlobEvent does not need to be zero.

## Syntax

    var timecode = blobEvent.timecode

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-blobevent-timecode">MediaStream Recording<br />
<span class="small">The definition of 'timecode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`timecode`

57

≤79

?

No

44

14

57

57

?

43

14

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent/timecode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent/timecode</a>
