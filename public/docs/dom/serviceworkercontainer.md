ServiceWorkerContainer
======================

The `ServiceWorkerContainer` interface of the [Service Worker API](service_worker_api) provides an object representing the service worker as an overall unit in the network ecosystem, including facilities to register, unregister and update service workers, and access the state of service workers and their registrations.

Most importantly, it exposes the [`ServiceWorkerContainer.register()`](serviceworkercontainer/register) method used to register service workers, and the [`ServiceWorkerContainer.controller`](serviceworkercontainer/controller) property used to determine whether or not the current page is actively controlled.

Properties
----------

 [`ServiceWorkerContainer.controller`](serviceworkercontainer/controller) <span class="badge inline readonly">Read only </span>   
Returns a [`ServiceWorker`](serviceworker) object if its state is `activating` or `activated` (the same object returned by [`ServiceWorkerRegistration.active`](serviceworkerregistration/active)). This property returns `null` during a force-refresh request (*Shift* + refresh) or if there is no active worker.

 [`ServiceWorkerContainer.ready`](serviceworkercontainer/ready) <span class="badge inline readonly">Read only </span>   
Provides a way of delaying code execution until a service worker is active. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will never reject, and which waits indefinitely until the [`ServiceWorkerRegistration`](serviceworkerregistration) associated with the current page has an [`ServiceWorkerRegistration.active`](serviceworkerregistration/active) worker. Once that condition is met, it resolves with the [`ServiceWorkerRegistration`](serviceworkerregistration).

Events
------

`controllerchange`  
Occurs when the document's associated [`ServiceWorkerRegistration`](serviceworkerregistration) acquires a new [`active`](serviceworkerregistration/active) worker.  
Also available via the [`ServiceWorkerContainer.oncontrollerchange`](serviceworkercontainer/oncontrollerchange) property.

`error`  
Fired whenever an error occurs in the associated service workers.

`message`  
Occurs when incoming messages are received by the [`ServiceWorkerContainer`](serviceworkercontainer) object (e.g. via a [`MessagePort.postMessage()`](messageport/postmessage) call.)  
Also available via the [`ServiceWorkerContainer.onmessage`](serviceworkercontainer/onmessage) property.

Methods
-------

 [`ServiceWorkerContainer.register()`](serviceworkercontainer/register)   
Creates or updates a [`ServiceWorkerRegistration`](serviceworkerregistration) for the given `scriptURL`.

[`ServiceWorkerContainer.getRegistration()`](serviceworkercontainer/getregistration)  
Gets a [`ServiceWorkerRegistration`](serviceworkerregistration) object whose scope matches the provided document URL. The method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`ServiceWorkerRegistration`](serviceworkerregistration) or `undefined`.

[`ServiceWorkerContainer.getRegistrations()`](serviceworkercontainer/getregistrations)  
Returns all [`ServiceWorkerRegistration`](serviceworkerregistration) objects associated with a `ServiceWorkerContainer` in an array. The method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`ServiceWorkerRegistration`](serviceworkerregistration).

[`ServiceWorkerContainer.startMessages()`](serviceworkercontainer/startmessages)  
explicitly starts the flow of messages being dispatched from a service worker to pages under its control (e.g. sent via [`Client.postMessage()`](client/postmessage)). This can be used to react to sent messages earlier, even before that page's content has finished loading.

Examples
--------

The example below first checks to see if the browser supports service workers. If supported, the code registers the service worker and determines if the page is actively controlled by the service worker. If it isn't, it prompts the user to reload the page so the service worker can take control. The code also reports any registration failures.

    if ('serviceWorker' in navigator) {
      // Register a service worker hosted at the root of the
      // site using the default scope.
      navigator.serviceWorker.register('/sw.js').then(function(registration) {
        console.log('Service worker registration succeeded:', registration);

        // At this point, you can optionally do something
        // with registration. See https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration
      }).catch(function(error) {
        console.log('Service worker registration failed:', error);
      });

      // Independent of the registration, let's also display
      // information about whether the current page is controlled
      // by an existing service worker, and when that
      // controller changes.

      // First, do a one-off check if there's currently a
      // service worker in control.
      if (navigator.serviceWorker.controller) {
        console.log('This page is currently controlled by:', navigator.serviceWorker.controller);
      }

      // Then, register a handler to detect when a new or
      // updated service worker takes control.
      navigator.serviceWorker.oncontrollerchange = function() {
        console.log('This page is now controlled by:', navigator.serviceWorker.controller);
      };
    } else {
      console.log('Service workers are not supported.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#serviceworkercontainer">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerContainer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ServiceWorkerContainer`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`controller`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`getRegistration`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`getRegistrations`

45

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

45

44

27

11.3

4.0

`message_event`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`oncontrollerchange`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`onerror`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`onmessage`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`onmessageerror`

No

17-79

Yes

No

?

Yes

No

No

Yes

?

Yes

No

`ready`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`register`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`startMessages`

74

≤79

64

No

62

Yes

74

74

64

50

Yes

11.0

See also
--------

-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer</a>
