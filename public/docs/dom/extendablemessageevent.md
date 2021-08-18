# ExtendableMessageEvent

The `ExtendableMessageEvent` interface of the [Service Worker API](service_worker_api) represents the event object of a `message` event fired on a service worker (when a message is received on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) from another context) — extends the lifetime of such events.

This interface inherits from the [`ExtendableEvent`](extendableevent) interface.

## Constructor

[`ExtendableMessageEvent()`](extendablemessageevent/extendablemessageevent)  
Creates a new `ExtendableMessageEvent` object instance.

## Properties

_Inherits properties from its parent, [`ExtendableEvent`](extendableevent)_.

[`ExtendableMessageEvent.data`](extendablemessageevent/data) <span class="badge inline readonly">Read only </span>  
Returns the event's data. It can be any data type.

[`ExtendableMessageEvent.origin`](extendablemessageevent/origin) <span class="badge inline readonly">Read only </span>  
Returns the origin of the [`Client`](client) that sent the message.

[`ExtendableMessageEvent.lastEventId`](extendablemessageevent/lasteventid) <span class="badge inline readonly">Read only </span>  
Represents, in [server-sent events](server-sent_events/using_server-sent_events), the last event ID of the event source. This is an empty string.

[`ExtendableMessageEvent.source`](extendablemessageevent/source) <span class="badge inline readonly">Read only </span>  
Returns a reference to the [`Client`](client) object that sent the message.

[`ExtendableMessageEvent.ports`](extendablemessageevent/ports) <span class="badge inline readonly">Read only </span>  
Returns the array containing the [`MessagePort`](messageport) objects representing the ports of the associated message channel.

## Methods

_Inherits methods from its parent, [`ExtendableEvent`](extendableevent)_.

## Examples

In the below example a page gets a handle to the [`ServiceWorker`](serviceworker) object via [`ServiceWorkerRegistration.active`](serviceworkerregistration/active), and then calls its `postMessage()` function.

    // in the page being controlled
    if (navigator.serviceWorker) {

      navigator.serviceWorker.register('service-worker.js');

      navigator.serviceWorker.addEventListener('message', event => {
        // event is a MessageEvent object
        console.log(`The service worker sent me a message: ${event.data}`);
      });

      navigator.serviceWorker.ready.then( registration => {
        registration.active.postMessage("Hi service worker");
      });

    }

The service worker can receive the message by listening to the `message` event:

    // in the service worker
    addEventListener('message', event => {
      // event is an ExtendableMessageEvent object
      console.log(`The client sent me a message: ${event.data}`);

      event.source.postMessage("Hi client");
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#extendablemessageevent">Service Workers<br />
<span class="small">The definition of 'ExtendableMessageEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ExtendableMessageEvent`

Yes

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

Yes

45

?

No

Yes

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

`data`

51

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

51

45

?

No

5.0

`lastEventId`

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

`origin`

?

17

No

No

?

No

No

?

No

?

No

?

`ports`

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

`source`

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

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [Service workers basic code example](https://github.com/mdn/sw-test)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [Channel Messaging](channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent</a>
