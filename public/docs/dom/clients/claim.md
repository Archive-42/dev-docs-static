# Clients.claim()

The `claim()` method of the [`Clients`](../clients) interface allows an active service worker to set itself as the [`controller`](../serviceworkercontainer/controller) for all clients within its [`scope`](../serviceworkerregistration/scope). This triggers a "`controllerchange`" event on [`navigator.serviceWorker`](../serviceworkercontainer) in any clients that become controlled by this service worker.

When a service worker is initially registered, pages won't use it until they next load. The `claim()` method causes those pages to be controlled immediately. Be aware that this results in your service worker controlling pages that loaded regularly over the network, or possibly via a different service worker.

## Syntax

    await clients.claim();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `undefined`.

## Example

The following example uses `claim()` inside service worker's "`activate`" event listener so that clients loaded in the same scope do not need to be reloaded before their fetches will go through this service worker.

    self.addEventListener('activate', event => {
      event.waitUntil(clients.claim());
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#clients-claim">Service Workers<br />
<span class="small">The definition of 'claim()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`claim`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

11.1

42

42

44

29

11.3

4.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [The service worker lifecycle](https://developers.google.com/web/fundamentals/instant-and-offline/service-worker/lifecycle)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promises`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [`self.skipWaiting()`](../serviceworkerglobalscope/skipwaiting) - skip the service worker's waiting phase

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim</a>
