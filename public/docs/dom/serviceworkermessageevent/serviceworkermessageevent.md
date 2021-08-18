ServiceWorkerMessageEvent.ServiceWorkerMessageEvent()
=====================================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Important**: In modern browsers, this property has been deprecated. Service worker messages will now use the [`MessageEvent`](../messageevent) interface, for consistency with other web messaging features.

The `ServiceWorkerMessageEvent()` constructor creates a new [`ServiceWorkerMessageEvent`](../serviceworkermessageevent) object instance.

Syntax
------

    var mySWME = new ServiceWorkerMessageEvent(type, init);

### Parameters

type  
A [`DOMString`](../domstring) that defines the type of the message event being created.

init <span class="badge inline optional">Optional</span>   
An initialization object, which should contain the following parameters:

-   `data`: The event's data — this can be any type.
-   `origin`: A [`DOMString`](../domstring) that defines the origin of the corresponding service worker's environment settings object.
-   `lastEventId`: A [`DOMString`](../domstring) that defines the last event ID of the event source.
-   `source`: The [`ServiceWorker`](../serviceworker) or [`MessagePort`](../messageport) that sent the message.
-   `ports`: An array containing the [`MessagePort`](../messageport) objects connected to the channel sending the message.

Examples
--------

    var init = {
                 data : 'hello message',
                 source : MessagePortReference,
                 ports : MessagePortListReference
               }

    var mySWME = new ServiceWorkerMessageEvent('message', init);

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

`ServiceWorkerMessageEvent`

45

17

44-55

\["[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.", "In Firefox 55 and later, the standard `MessageEvent` interface must be used instead."\]

No

24

No

No

45

44-55

24

No

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Channel Messaging](../channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent/ServiceWorkerMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent/ServiceWorkerMessageEvent</a>
