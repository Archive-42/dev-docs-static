ProgressEvent.total
===================

The `ProgressEvent.total` read-only property is an unsigned 64-bit integer value indicating the total size of the data being processed or transmitted. In the case of an HTTP transmission, this is the size of the body of the message (the `Content-Length`), and does not include headers and other overhead.

If the event's [`lengthComputable`](lengthcomputable) property is `false`, this value is meaningless and should be ignored.

Syntax
------

    let value = progressEvent.total;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-progressevent-total">XMLHttpRequest<br />
<span class="small">The definition of 'ProgressEvent.lengthComputable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`total`

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

See also
--------

-   The [`ProgressEvent`](../progressevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/total" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/total</a>
