ServiceWorkerGlobalScope: push event
====================================

The `push` event is sent to a service worker's global scope (represented by the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface) when the service worker has received a push message.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pushevent"><code>PushEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onpush"><code>onpush</code></a></td></tr></tbody></table>

Example
-------

This example sets up a handler for `push` events that takes [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) data, parses it, and dispatches the message for handling based on information contained within the message.

    self.addEventListener("push", event => {
      let message = event.data.json();

      switch(message.type) {
        case "init":
          doInit();
          break;
        case "shutdown":
          doShutdown();
          break;
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#extensions-to-the-serviceworkerglobalscope-interface">Push API<br />
<span class="small">The definition of 'push' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`push_event`

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

See also
--------

-   [Using the Push API](../push_api)
-   [`onpush`](onpush) event handler property
-   [`pushsubscriptionchange`](pushsubscriptionchange_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/push_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/push_event</a>
