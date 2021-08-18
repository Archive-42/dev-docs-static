# Client.frameType

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `frameType` read-only property of the [`Client`](../client) interface indicates the type of browsing context of the current [`Client`](../client). This value can be one of `"auxiliary"`, `"top-level"`, `"nested"`, or `"none"`.

## Syntax

    var myFrameType = client.frameType;

## Example

    TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#client-frametype">Service Workers<br />
<span class="small">The definition of 'frameType' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`frameType`

43

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

30

11.1

43

43

44

30

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Client/frameType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Client/frameType</a>
