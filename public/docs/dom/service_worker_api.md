Service Worker API
==================

Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available). They are intended, among other things, to enable the creation of effective offline experiences, intercept network requests and take appropriate action based on whether the network is available, and update assets residing on the server. They will also allow access to push notifications and background sync APIs.

Service worker concepts and usage
---------------------------------

A service worker is an event-driven [worker](worker) registered against an origin and a path. It takes the form of a JavaScript file that can control the web-page/site that it is associated with, intercepting and modifying navigation and resource requests, and caching resources in a very granular fashion to give you complete control over how your app behaves in certain situations (the most obvious one being when the network is not available).

A service worker is run in a worker context: it therefore has no DOM access, and runs on a different thread to the main JavaScript that powers your app, so it is non-blocking. It is designed to be fully async; as a consequence, APIs such as synchronous [XHR](xmlhttprequest) and [Web Storage](web_storage_api) can't be used inside a service worker.

Service workers only run over HTTPS, for security reasons. Having modified network requests, wide open to *man in the middle* attacks would be really bad. In Firefox, Service Worker APIs are also hidden and cannot be used when the user is in [private browsing mode](https://support.mozilla.org/en-US/kb/private-browsing-use-firefox-without-history).

**Tip**

On Firefox, for testing you can run service workers over HTTP (insecurely); simply check the **Enable Service Workers over HTTP (when toolbox is open)** option in the Firefox Devtools options/gear menu.

**Note**

Unlike previous attempts in this area such as [AppCache](https://alistapart.com/article/application-cache-is-a-douchebag), service workers don't make assumptions about what you are trying to do, but then break when those assumptions are not exactly right. Instead, service workers give you much more granular control.

**Note**

Service workers make heavy use of [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), as generally they will wait for responses to come through, after which they will respond with a success or failure action. The promises architecture is ideal for this.

### Registration

A service worker is first registered using the [`ServiceWorkerContainer.register()`](serviceworkercontainer/register) method. If successful, your service worker will be downloaded to the client and attempt installation/activation (see below) for URLs accessed by the user inside the whole origin, or inside a subset specified by you.

### Download, install and activate

At this point, your service worker will observe the following lifecycle:

1.  Download
2.  Install
3.  Activate

The service worker is immediately downloaded when a user first accesses a service worker–controlled site/page.

After that, it is updated when:

-   A navigation to an in-scope page occurs.
-   An event is fired on the service worker and it hasn't been downloaded in the last 24 hours.

Installation is attempted when the downloaded file is found to be new — either different to an existing service worker (byte-wise compared), or the first service worker encountered for this page/site.

If this is the first time a service worker has been made available, installation is attempted, then after a successful installation, it is activated.

If there is an existing service worker available, the new version is installed in the background, but not yet activated — at this point it is called the *worker in waiting*. It is only activated when there are no longer any pages loaded that are still using the old service worker. As soon as there are no more pages to be loaded, the new service worker activates (becoming the *active worker*). Activation can happen sooner using [`ServiceWorkerGlobalScope.skipWaiting()`](serviceworkerglobalscope/skipwaiting) and existing pages can be claimed by the active worker using [`Clients.claim()`](clients/claim).

You can listen for the [`install`](serviceworkerglobalscope/install_event) event; a standard action is to prepare your service worker for usage when this fires, for example by creating a cache using the built in storage API, and placing assets inside it that you'll want for running your app offline.

There is also an [`activate`](serviceworkerglobalscope/activate_event) event. The point where this event fires is generally a good time to clean up old caches and other things associated with the previous version of your service worker.

Your service worker can respond to requests using the [`FetchEvent`](fetchevent) event. You can modify the response to these requests in any way you want, using the [`FetchEvent.respondWith()`](fetchevent/respondwith) method.

**Note**

Because `install`/`activate` events could take a while to complete, the service worker spec provides a [`waitUntil()`](extendableevent/waituntil) method. Once it is called on `install` or `activate` events with a promise, functional events such as `fetch` and `push` will wait until the promise is successfully resolved.

For a complete tutorial to show how to build up your first basic example, read [Using Service Workers](service_worker_api/using_service_workers).

Other use case ideas
--------------------

Service workers are also intended to be used for such things as:

-   Background data synchronization.
-   Responding to resource requests from other origins.
-   Receiving centralized updates to expensive-to-calculate data such as geolocation or gyroscope, so multiple pages can make use of one set of data.
-   Client-side compiling and dependency management of CoffeeScript, less, CJS/AMD modules, etc. for development purposes.
-   Hooks for background services.
-   Custom templating based on certain URL patterns.
-   Performance enhancements, for example pre-fetching resources that the user is likely to need in the near future, such as the next few pictures in a photo album.

In the future, service workers will be able to do a number of other useful things for the web platform that will bring it closer towards native app viability. Interestingly, other specifications can and will start to make use of the service worker context, for example:

-   [Background synchronization](https://github.com/slightlyoff/BackgroundSync): Start up a service worker even when no users are at the site, so caches can be updated, etc.
-   [Reacting to push messages](push_api): Start up a service worker to send users a message to tell them new content is available.
-   Reacting to a particular time & date.
-   Entering a geo-fence.

Interfaces
----------

 [`Cache`](cache) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents the storage for [`Request`](request) / [`Response`](response) object pairs that are cached as part of the [`ServiceWorker`](serviceworker) life cycle.

 [`CacheStorage`](cachestorage) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents the storage for [`Cache`](cache) objects. It provides a master directory of all the named caches that a [`ServiceWorker`](serviceworker) can access, and maintains a mapping of string names to corresponding [`Cache`](cache) objects.

 [`Client`](client) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents the scope of a service worker client. A service worker client is either a document in a browser context or a [`SharedWorker`](sharedworker), which is controlled by an active worker.

 [`Clients`](clients) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents a container for a list of [`Client`](client) objects; the main way to access the active service worker clients at the current origin.

 [`ExtendableEvent`](extendableevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Extends the lifetime of the `install` and `activate` events dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope), as part of the service worker lifecycle. This ensures that any functional events (like [`FetchEvent`](fetchevent)) are not dispatched to the [`ServiceWorker`](serviceworker), until it upgrades database schemas, and deletes outdated cache entries, etc.

 [`ExtendableMessageEvent`](extendablemessageevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The event object of a [`ServiceWorkerGlobalScope/message_event`](serviceworkerglobalscope/message_event) event fired on a service worker (when a channel message is received on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) from another context) — extends the lifetime of such events.

 [`FetchEvent`](fetchevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The parameter passed into the [`ServiceWorkerGlobalScope.onfetch`](serviceworkerglobalscope/onfetch) handler, `FetchEvent` represents a fetch action that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). It contains information about the request and resulting response, and provides the [`FetchEvent.respondWith()`](fetchevent/respondwith) method, which allows us to provide an arbitrary response back to the controlled page.

 [`InstallEvent`](installevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The parameter passed into the [`oninstall`](serviceworkerglobalscope/oninstall) handler, the `InstallEvent` interface represents an install action that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). As a child of [`ExtendableEvent`](extendableevent), it ensures that functional events such as [`FetchEvent`](fetchevent) are not dispatched during installation.

 [`NavigationPreloadManager`](navigationpreloadmanager) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Provides methods for managing the preloading of resources with a service worker.

[`Navigator.serviceWorker`](navigator/serviceworker)  
Returns a [`ServiceWorkerContainer`](serviceworkercontainer) object, which provides access to registration, removal, upgrade, and communication with the [`ServiceWorker`](serviceworker) objects for the [associated document](https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window).

 [`NotificationEvent`](notificationevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The parameter passed into the [`onnotificationclick`](serviceworkerglobalscope/onnotificationclick) handler, the `NotificationEvent` interface represents a notification click event that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker).

 [`ServiceWorker`](serviceworker) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents a service worker. Multiple browsing contexts (e.g. pages, workers, etc.) can be associated with the same `ServiceWorker` object.

 [`ServiceWorkerContainer`](serviceworkercontainer) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Provides an object representing the service worker as an overall unit in the network ecosystem, including facilities to register, unregister, and update service workers, and access the state of service workers and their registrations.

[`ServiceWorkerGlobalScope`](serviceworkerglobalscope)  
Represents the global execution context of a service worker.

 [`ServiceWorkerMessageEvent`](serviceworkermessageevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Represents a message sent to a [`ServiceWorkerGlobalScope`](serviceworkerglobalscope). **Note that this interface is deprecated in modern browsers. Service worker messages will now use the [`MessageEvent`](messageevent) interface, for consistency with other web messaging features.**

 [`ServiceWorkerRegistration`](serviceworkerregistration) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents a service worker registration.

 [`ServiceWorkerState`](serviceworkerstate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Associated with its [`ServiceWorker`](serviceworker)'s state.

 [`SyncEvent`](syncevent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The SyncEvent interface represents a sync action that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a ServiceWorker.

 [`SyncManager`](syncmanager) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Provides an interface for registering and listing sync registrations.

 [`WindowClient`](windowclient) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Represents the scope of a service worker client that is a document in a browser context, controlled by an active worker. This is a special type of [`Client`](client) object, with some additional methods and properties available.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/">Service Workers</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

See also
--------

-   [ServiceWorker Cookbook](https://serviceworke.rs)
-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API</a>
