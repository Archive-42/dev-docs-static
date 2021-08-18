InstallEvent
============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The parameter passed into the [`oninstall`](serviceworkerglobalscope/oninstall) handler, the `InstallEvent` interface represents an install action that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). As a child of [`ExtendableEvent`](extendableevent), it ensures that functional events such as [`FetchEvent`](fetchevent) are not dispatched during installation.

This interface inherits from the [`ExtendableEvent`](extendableevent) interface.

Constructor
-----------

[`InstallEvent.InstallEvent()`](installevent/installevent)  
Creates a new `InstallEvent` object.

Properties
----------

*Inherits properties from its ancestor, [`Event`](event)*.

 [`InstallEvent.activeWorker`](installevent/activeworker) <span class="badge inline readonly">Read only </span>   
Returns the [`ServiceWorker`](serviceworker) that is currently controlling the page.

Methods
-------

*Inherits methods from its parent, [`ExtendableEvent`](extendableevent)*.

Examples
--------

This code snippet is from the [service worker prefetch sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/prefetch/service-worker.js) (see [prefetch running live](https://googlechrome.github.io/samples/service-worker/prefetch/).) The code calls [`ExtendableEvent.waitUntil()`](extendableevent/waituntil) in [`ServiceWorkerGlobalScope.oninstall`](serviceworkerglobalscope/oninstall) and delays treating the [`ServiceWorkerRegistration.installing`](serviceworkerregistration/installing) worker as installed until the passed promise resolves successfully. The promise resolves when all resources have been fetched and cached, or when any exception occurs.

The code snippet also shows a best practice for versioning caches used by the service worker. Although this example has only one cache, you can use this approach for multiple caches. The code maps a shorthand identifier for a cache to a specific, versioned cache name.

**Note**: Logging statements are visible in Google Chrome via the "Inspect" interface for the relevant service worker accessed via chrome://serviceworker-internals.

    var CACHE_VERSION = 1;
    var CURRENT_CACHES = {
      prefetch: 'prefetch-cache-v' + CACHE_VERSION
    };

    self.addEventListener('install', function(event) {
      var urlsToPrefetch = [
        './static/pre_fetched.txt',
        './static/pre_fetched.html',
        'https://www.chromium.org/_/rsrc/1302286216006/config/customLogo.gif'
      ];

    console.log('Handling install event. Resources to pre-fetch:', urlsToPrefetch);

      event.waitUntil(
        caches.open(CURRENT_CACHES['prefetch']).then(function(cache) {
          return cache.addAll(urlsToPrefetch.map(function(urlToPrefetch) {
            return new Request(urlToPrefetch, {mode: 'no-cors'});
          })).then(function() {
            console.log('All resources have been fetched and cached.');
          });
        }).catch(function(error) {
          console.error('Pre-fetching failed:', error);
        })
      );
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

`InstallEvent`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

`InstallEvent`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

`activeWorker`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

See also
--------

-   [`NotificationEvent`](notificationevent)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Fetch API](fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent</a>
