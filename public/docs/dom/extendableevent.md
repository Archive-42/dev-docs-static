# ExtendableEvent

The `ExtendableEvent` interface extends the lifetime of the `install` and `activate` events dispatched on the global scope as part of the service worker lifecycle. This ensures that any functional events (like [`FetchEvent`](fetchevent)) are not dispatched until it upgrades database schemas and deletes the outdated cache entries.

If [`waitUntil()`](extendableevent/waituntil) is called outside of the `ExtendableEvent` handler, the browser should throw an `InvalidStateError`; note also that multiple calls will stack up, and the resulting promises will be added to the list of [extend lifetime promises](https://w3c.github.io/ServiceWorker/#extendableevent-extend-lifetime-promises).

**Note**: The behavior described in the above paragraph was fixed in Firefox 43 (see [bug 1180274](https://bugzilla.mozilla.org/show_bug.cgi?id=1180274).)

This interface inherits from the [`Event`](event) interface.

**Note**: This interface is only available when the global scope is a [`ServiceWorkerGlobalScope`](serviceworkerglobalscope). It is not available when it is a [`Window`](window), or the scope of another kind of worker.

## Constructor

[`ExtendableEvent()`](extendableevent/extendableevent)  
Creates a new `ExtendableEvent` object.

## Properties

_Doesn't implement any specific properties, but inherits properties from its parent, [`Event`](event)._

## Methods

_Inherits methods from its parent, [`Event`](event)_.

[`ExtendableEvent.waitUntil()`](extendableevent/waituntil)  
Extends the lifetime of the event. It is intended to be called in the `install` [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the [`installing`](serviceworkerregistration/installing) worker and on the `activate` [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the [`active`](serviceworkerregistration/active) worker.

## Examples

This code snippet is from the [service worker prefetch sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/prefetch/service-worker.js) (see [prefetch example live](https://googlechrome.github.io/samples/service-worker/prefetch/).) The code calls [`ExtendableEvent.waitUntil()`](extendableevent/waituntil) in [`ServiceWorkerGlobalScope.oninstall`](serviceworkerglobalscope/oninstall), delaying treating the [`ServiceWorkerRegistration.installing`](serviceworkerregistration/installing) worker as installed until the passed promise resolves successfully. The promise resolves when all resources have been fetched and cached, or else when any exception occurs.

The code snippet also shows a best practice for versioning caches used by the service worker. Though there's only one cache in this example, the same approach can be used for multiple caches. It maps a shorthand identifier for a cache to a specific, versioned cache name.

**Note**: In Chrome, logging statements are visible via the "Inspect" interface for the relevant service worker accessed via chrome://serviceworker-internals.

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

**Important**: When fetching resources, it's very important to use `{mode: 'no-cors'}` if there is any chance that the resources are served off of a server that doesn't support [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS). In this example, [www.chromium.org](https://www.chromium.org) doesn't support CORS.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#extendableevent">Service Workers<br />
<span class="small">The definition of 'ExtendableEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ExtendableEvent`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

No

40

40

44

24

No

4.0

`ExtendableEvent`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

No

40

40

44

24

No

4.0

`waitUntil`

40

17

44

No

24

No

40

40

44

24

No

4.0

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [Service workers basic code example](https://github.com/mdn/sw-test)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent</a>
