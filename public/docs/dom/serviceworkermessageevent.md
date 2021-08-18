ServiceWorkerMessageEvent
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Important**: In modern browsers, this interface has been deprecated. Service worker messages will now use the [`MessageEvent`](messageevent) interface, for consistency with other web messaging features.

The `ServiceWorkerMessageEvent` interface of the [`ServiceWorker API`](service_worker_api) contains information about an event sent to a [`ServiceWorkerContainer`](serviceworkercontainer) target. This extends the default `message` event to allow setting a [`ServiceWorker`](serviceworker) object as the source of a message. The event object is accessed via the handler function of a `message` event, when fired by a message received from a service worker.

This interface inherits from the [`Event`](event) interface.

Constructor
-----------

 [`ServiceWorkerMessageEvent.ServiceWorkerMessageEvent()`](serviceworkermessageevent/serviceworkermessageevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Creates a new `ServiceWorkerMessageEvent` object instance.

Properties
----------

*Inherits properties from its parent, [`Event`](event)*.

 [`ServiceWorkerMessageEvent.data`](serviceworkermessageevent/data) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the event's data. It can be any data type.

 [`ServiceWorkerMessageEvent.origin`](serviceworkermessageevent/origin) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the origin of the service worker's environment settings object.

 [`ServiceWorkerMessageEvent.lastEventId`](serviceworkermessageevent/lasteventid) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Represents, in [server-sent events](en-us/docs/server-sent_events/using_server-sent_events), the last event ID of the event source.

 [`ServiceWorkerMessageEvent.source`](serviceworkermessageevent/source) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a reference to the service worker that sent the message.

 [`ServiceWorkerMessageEvent.ports`](serviceworkermessageevent/ports) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an array of [`MessagePort`](messageport) objects.

Methods
-------

*Inherits methods from its parent, [`Event`](event)*.

Examples
--------

When the following code is used inside the main thread to set up a message channel between it and a service worker for sending messages between the two, the event object of `onmessage` will be a `ServiceWorkerMessageEvent`.

    navigator.serviceWorker.ready.then(function(reg) {

      ...

          // set up a message channel to communicate with the SW
          var channel = new MessageChannel();
          channel.port1.onmessage = function(e) {
            console.log(e);
            handleChannelMessage(e.data);
          }

          mySW = reg.active;
          mySW.postMessage('hello', [channel.port2]);
      });

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

`data`

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

`lastEventId`

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

`origin`

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

`ports`

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

`source`

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

-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent</a>
