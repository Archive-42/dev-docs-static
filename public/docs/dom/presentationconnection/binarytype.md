# PresentationConnection.binaryType

When a [`PresentationConnection`](../presentationconnection) object is created, its `binaryType` IDL attribute _MUST_ be set to the string `"arraybuffer"`. Upon getting, the attribute _MUST_ return its most recent value (the value it was last set as). Upon setting, the user agent _MUST_ set the IDL attribute to the new value.

**Note:** The `binaryType` attribute allows authors to control how binary data is exposed to scripts. By setting the attribute to `"blob"`, binary data is returned in `Blob` form; by setting it to `"arraybuffer"`, it is returned in [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) form. The attribute defaults to `"arraybuffer"`. This attribute has no effect on data sent in a string form.

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

`binaryType`

Yes

≤79

51-88

No

Yes

No

No

Yes

51-79

Yes

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/binaryType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/binaryType</a>
