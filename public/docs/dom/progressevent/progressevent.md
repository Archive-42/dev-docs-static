ProgressEvent()
===============

The `ProgressEvent()` constructor returns a newly created [`ProgressEvent`](../progressevent), representing the current completion of a long process.

Syntax
------

    progressEvent = new ProgressEvent(type, {lengthComputable: aBooleanValue, loaded: aNumber, total: aNumber});

### Arguments

*The `ProgressEvent()` constructor also inherits arguments from [`Event()`](../event/event).*

*type*  
Is a [`DOMString`](../domstring) representing the name of the type of the `ProgressEvent`. It is case-sensitive.

 `lengthComputable` <span class="badge inline optional">Optional</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the total work to be done, and the amount of work already done, by the underlying process is calculable. In other words, it tells if the progress is measurable or not. It defaults to `false`.

 `loaded` <span class="badge inline optional">Optional</span>   
Is an `unsigned long long` representing the amount of work already performed by the underlying process. The ratio of work done can be calculated with the property and `ProgressEvent.total`. When downloading a resource using HTTP, this only represent the part of the content itself, not headers and other overhead. It defaults to `0`.

 `total` <span class="badge inline optional">Optional</span>   
Is an `unsigned long long` representing the total amount of work that the underlying process is in the progress of performing. When downloading a resource using HTTP, this only represent the content itself, not headers and other overhead. It defaults to `0`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-progressevent-progressevent">XMLHttpRequest<br />
<span class="small">The definition of 'ProgressEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ProgressEvent`

Yes

≤79

22

No

Yes

Yes

Yes

Yes

22

Yes

Yes

Yes

See also
--------

-   The [`ProgressEvent`](../progressevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/ProgressEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/ProgressEvent</a>
