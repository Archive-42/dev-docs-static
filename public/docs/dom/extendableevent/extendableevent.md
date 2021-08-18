ExtendableEvent()
=================

The `ExtendableEvent()` constructor creates a new [`ExtendableEvent`](../extendableevent) object.

Syntax
------

    var extendableEvent = new ExtendableEvent(type, init);

### Parameters

`type`  
The type of the ExtendableEvent, for example `install`, `activate`.

 `init` <span class="badge inline optional">Optional</span>   
An options object containing any custom settings that you want to apply to the event object. Currently no possible options exist inside the spec, but this has been defined for forward compatibility across the different derived events.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-extendableevent-extendableevent">Service Workers<br />
<span class="small">The definition of 'ExtendableEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ExtendableEvent`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

No

40

40

44

24

No

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/ExtendableEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/ExtendableEvent</a>
