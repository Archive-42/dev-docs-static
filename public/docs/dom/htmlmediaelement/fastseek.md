# HTMLMediaElement.fastSeek()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLMediaElement.fastSeek()` method quickly seeks the media to the new time with precision tradeoff.

**Note:** If you need to seek with precision, you should set [`HTMLMediaElement.currentTime`](currenttime) instead.

## Syntax

    HTMLMediaElement.fastSeek(time);

### Parameters

time  
A double.

### Return value

None.

## Example

This example quickly seeks to 20-second position of the video element.

    let myVideo = document.getElementById("myVideoElement");

    myVideo.fastSeek(20);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-fastseek">HTML Living Standard<br />
<span class="small">The definition of 'fastSeek()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition; living specification.</td></tr></tbody></table>

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

`fastSeek`

No

No

31

No

No

6.1

No

?

31

No

6.1

?

## See also

- [HTMLMediaElement.currentTime](currenttime) for seeking without precision tradeoff

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/fastSeek" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/fastSeek</a>
