ServiceWorker
=============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `ServiceWorker` interface of the [Service Worker API](service_worker_api) provides a reference to a service worker. Multiple [browsing contexts](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) (e.g. pages, workers, etc.) can be associated with the same service worker, each through a unique `ServiceWorker` object.

A `ServiceWorker` object is available in the [`ServiceWorkerRegistration.active`](serviceworkerregistration/active) property, and the [`ServiceWorkerContainer.controller`](serviceworkercontainer/controller) property — this is a service worker that has been activated and is controlling the page (the service worker has been successfully registered, and the controlled page has been reloaded.)

The `ServiceWorker` interface is dispatched a set of lifecycle events — `install` and `activate` — and functional events including `fetch`. A `ServiceWorker` object has an associated [`ServiceWorker.state`](serviceworker/state), related to its lifecycle.

Properties
----------

*The `ServiceWorker` interface inherits properties from its parent, [`Worker`](worker).*

 [`ServiceWorker.scriptURL`](serviceworker/scripturl) <span class="badge inline readonly">Read only </span>   
Returns the `ServiceWorker` serialized script URL defined as part of [`ServiceWorkerRegistration`](serviceworkerregistration). The URL must be on the same origin as the document that registers the `ServiceWorker`.

 [`ServiceWorker.state`](serviceworker/state) <span class="badge inline readonly">Read only </span>   
Returns the state of the service worker. It returns one of the following values: `installing`, `installed,` `activating`, `activated`, or `redundant`.

### Event handlers

 [`ServiceWorker.onstatechange`](serviceworker/onstatechange) <span class="badge inline readonly">Read only </span>   
An [`EventListener`](eventlistener) property called whenever an event of type `statechange` is fired; it is basically fired anytime the [`ServiceWorker.state`](serviceworker/state) changes.

Methods
-------

*The `ServiceWorker` interface inherits methods from its parent, [`Worker`](worker), with the exception of [`Worker.terminate`](worker/terminate) — this should not be accessible from service workers.*

Examples
--------

This code snippet is from the [service worker registration-events sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/registration-events/index.html) ([live demo](https://googlechrome.github.io/samples/service-worker/registration-events/)). The code listens for any change in the [`ServiceWorker.state`](serviceworker/state) and returns its value.

    if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('service-worker.js', {
            scope: './'
        }).then(function (registration) {
            var serviceWorker;
            if (registration.installing) {
                serviceWorker = registration.installing;
                document.querySelector('#kind').textContent = 'installing';
            } else if (registration.waiting) {
                serviceWorker = registration.waiting;
                document.querySelector('#kind').textContent = 'waiting';
            } else if (registration.active) {
                serviceWorker = registration.active;
                document.querySelector('#kind').textContent = 'active';
            }
            if (serviceWorker) {
                // logState(serviceWorker.state);
                serviceWorker.addEventListener('statechange', function (e) {
                    // logState(e.target.state);
                });
            }
        }).catch (function (error) {
            // Something went wrong during registration. The service-worker.js file
            // might be unavailable or contain a syntax error.
        });
    } else {
        // The current browser doesn't support service workers.
        // Perhaps it is too old or we are not in a Secure Context.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#serviceworker">Service Workers<br />
<span class="small">The definition of 'ServiceWorker' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ServiceWorker`

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

`onstatechange`

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

`postMessage`

40

17

44

No

27

11.1

40

40

44

27

11.3

4.0

`scriptURL`

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

`state`

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

See also
--------

-   [ServiceWorker Cookbook](https://serviceworke.rs)
-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service worker basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker</a>
