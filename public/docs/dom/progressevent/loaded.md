# ProgressEvent.loaded

The `ProgressEvent.loaded` read-only property is an integer representing the amount of work already performed by the underlying process. The ratio of work done can be calculated with the property and `ProgressEvent.total`. When downloading a resource using HTTP, this only represent the part of the content itself, not headers and other overhead.

## Syntax

    value = ProgressEvent.loaded

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-progressevent-loaded">XMLHttpRequest<br />
<span class="small">The definition of 'ProgressEvent.loaded' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`loaded`

Yes

12

3.5

No

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

## See also

- The [`ProgressEvent`](../progressevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/loaded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/loaded</a>
