XMLHttpRequestEventTarget
=========================

`XMLHttpRequestEventTarget` is the interface that describes the event handlers you can implement in an object that will handle events for an [`XMLHttpRequest`](xmlhttprequest).

Properties
----------

[`XMLHttpRequestEventTarget.onabort`](xmlhttprequesteventtarget/onabort)  
Contains the function to call when a request is aborted and the `abort` event is received by this object.

[`XMLHttpRequestEventTarget.onerror`](xmlhttprequesteventtarget/onerror)  
Contains the function to call when a request encounters an error and the `error` event is received by this object.

[`XMLHttpRequestEventTarget.onload`](xmlhttprequesteventtarget/onload)  
Contains the function to call when an HTTP request returns after successfully fetching content and the `load` event is received by this object.

[`XMLHttpRequestEventTarget.onloadstart`](xmlhttprequesteventtarget/onloadstart)  
Contains the function that gets called when the HTTP request first begins loading data and the `loadstart` event is received by this object.

[`XMLHttpRequestEventTarget.onprogress`](xmlhttprequesteventtarget/onprogress)  
Contains the function that is called periodically with information about the progress of the request and the `progress` event is received by this object.

<span class="page-not-created">`XMLHttpRequestEventTarget.ontimeout`</span>  
Contains the function that is called if the event times out and the `timeout` event is received by this object; this only happens if a timeout has been previously established by setting the value of the `XMLHttpRequest` object's `timeout` attribute.

<span class="page-not-created">`XMLHttpRequestEventTarget.onloadend`</span>  
Contains the function that is called when the load is completed, even if the request failed, and the `loadend` event is received by this object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`XMLHttpRequestEventTarget`

1

12

1

7

Yes

1

1

18

Yes

Yes

Yes

1.0

`onabort`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onerror`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onload`

Yes

≤18

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onloadend`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onloadstart`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onprogress`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`ontimeout`

Yes

≤18

Yes

8

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`XMLHttpRequest`](xmlhttprequest)
-   [Using XMLHttpRequest](xmlhttprequest/using_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget</a>
