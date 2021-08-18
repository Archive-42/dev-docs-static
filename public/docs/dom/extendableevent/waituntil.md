# ExtendableEvent.waitUntil()

The `ExtendableEvent.waitUntil()` method tells the event dispatcher that work is ongoing. It can also be used to detect whether that work was successful. In service workers, `waitUntil()` tells the browser that work is ongoing until the promise settles, and it shouldn't terminate the service worker if it wants that work to complete.

The [`install`](../serviceworkerglobalscope/install_event) events in [service workers](../serviceworkerglobalscope) use `waitUntil()` to hold the service worker in the [`installing`](../serviceworkerregistration/installing) phase until tasks complete. If the promise passed to `waitUntil()` rejects, the install is considered a failure, and the installing service worker is discarded. This is primarily used to ensure that a service worker is not considered installed until all of the core caches it depends on are successfully populated.

The [`activate`](../serviceworkerglobalscope/activate_event) events in [service workers](../serviceworkerglobalscope) use `waitUntil()` to buffer functional events such as `fetch` and `push` until the promise passed to `waitUntil()` settles. This gives the service worker time to update database schemas and delete outdated [`caches`](../cache), so other events can rely on a completely upgraded state.

The `waitUntil()` method must be initially called within the event callback, but after that it can be called multiple times, until all the promises passed to it settle.

**Note**: The behavior described in the above paragraph was fixed in Firefox 43 (see [bug 1180274](https://bugzilla.mozilla.org/show_bug.cgi?id=1180274)).

## Syntax

    extendableEvent.waitUntil(promise);

### Parameters

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Example

Using `waitUntil()` within a service worker's `install` event:

    addEventListener('install', event => {
      const preCache = async () => {
        const cache = await caches.open('static-v1');
        return cache.addAll([
          '/',
          '/about/',
          '/static/styles.css'
        ]);
      };
      event.waitUntil(preCache());
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-extendableevent-waituntil">Service Workers<br />
<span class="small">The definition of 'waitUntil()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`async_waitUntil`

?

17

53

No

?

No

?

?

53

?

No

?

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/waitUntil" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/waitUntil</a>
