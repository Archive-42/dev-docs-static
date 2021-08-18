# FetchEvent.isReload

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `isReload` read-only property of the [`FetchEvent`](../fetchevent) interface returns `true` if the event was dispatched by the user attempting to reload the page, and `false` otherwise. Pressing the refresh button is a reload while clicking a link and pressing the back button is not.

## Syntax

    var reloaded = FetchEvent.isReload

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Example

    self.addEventListener('fetch', function(event) {
      event.respondWith(
        if (event.isReload) {
          //Return something
        } else {
          //Return something else
        };
      );
    });

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

`isReload`

45

17

44-74

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

No

45

45

44

32

No

5.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [Service workers basic code example](https://github.com/mdn/sw-test)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/isReload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/isReload</a>
