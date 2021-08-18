ServiceWorkerGlobalScope.onmessage
==================================

The **onmessage** property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is an event handler fired whenever a [`message`](message_event) event occurs — when incoming messages are received.

**Note**: Service workers define the extendable event to allow extending the lifetime of the event. For the `message` event, service workers use the [`ExtendableMessageEvent`](../extendablemessageevent) interface which extends the [`ExtendableEvent`](../extendableevent) interface.

**Note**: Messages received from service worker contexts (e.g. as the event object of `onmessage`) are represented by [`MessageEvent`](../messageevent) objects in modern browsers, for consistency with other web messaging features. (They used to be represented by [`ServiceWorkerMessageEvent`](../serviceworkermessageevent) objects, which have now been deprecated.)

Syntax
------

    serviceWorkerGlobalScope.onmessage = function(extendableMessageEvent) { ... };

Example
-------

    self.addEventListener('message', function(messageEvent) {
      console.log('Handling message event:', messageEvent);
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-event-handlers">Service Workers<br />
<span class="small">The definition of 'Event Handlers' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onmessage`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

40

40

44

24

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onmessage</a>
