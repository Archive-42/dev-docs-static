# BlobEvent.BlobEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BlobEvent()` constructor returns a newly created [`BlobEvent`](../blobevent) object with an associated [`Blob`](../blob).

## Syntax

    blobEvent = new BlobEvent({data: aSpecificBlob}[, timecode]);

### Arguments

_The `BlobEvent()` constructor also inherits arguments from [`Event()`](../event/event)._

`data`  
Is a [`Blob`](../blob) associated with the event.

`timecode` <span class="badge inline optional">Optional</span>  
A [`DOMHighResTimeStamp`](../domhighrestimestamp) to be used in initializing the blob event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-blobevent-blobevent">MediaStream Recording<br />
<span class="small">The definition of 'BlobEvent: BlobEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BlobEvent`

49

≤79

22

No

36

14

49

49

22

36

14

5.0

## See also

- The [`BlobEvent`](../blobevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent/BlobEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent/BlobEvent</a>
