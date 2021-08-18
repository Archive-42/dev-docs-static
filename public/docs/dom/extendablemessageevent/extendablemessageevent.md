ExtendableMessageEvent()
========================

The `Extendable``MessageEvent()` constructor creates a new [`ExtendableMessageEvent`](../extendablemessageevent) object instance.

Syntax
------

    var extendableMessageEvent = new ExtendableMessageEvent(type, init);

### Parameters

type  
A [`DOMString`](../domstring) that defines the type of the message event being created.

init <span class="badge inline optional">Optional</span>   
An initialization object, which should contain the following parameters:

-   `data`: The event's data — this can be any data type.
-   `origin`: A [`DOMString`](../domstring) that defines the origin of the corresponding service worker's environment settings object.
-   `lastEventId`: A [`DOMString`](../domstring) that defines the last event ID of the event source.
-   `source`: The [`Client`](../client), [`ServiceWorker`](../serviceworker) or [`MessagePort`](../messageport) that sent the message.
-   `ports`: An array containing the [`MessagePort`](../messageport) objects connected to the channel sending the message.

Examples
--------

    var init = {
                 data : 'hello message',
                 source : MessagePortReference,
                 ports : MessagePortListReference
               }

    var myEME = new ExtendableMessageEvent('message', init);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-extendablemessageevent-extendablemessageevent">Service Workers<br />
<span class="small">The definition of 'ExtendableMessageEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ExtendableMessageEvent`

?

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

?

45

?

No

?

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Channel Messaging](../channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent/ExtendableMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent/ExtendableMessageEvent</a>
