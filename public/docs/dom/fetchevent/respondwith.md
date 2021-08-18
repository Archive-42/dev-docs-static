FetchEvent.respondWith()
========================

The `respondWith()` method of [`FetchEvent`](../fetchevent) prevents the browser's default fetch handling, and allows you to provide a promise for a [`Response`](../response) yourself.

In most cases you can provide any response that the receiver understands. For example, if an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) initiates the request, the response body needs to be image data. For security reasons, there are a few global rules:

-   You can only return [`Response`](../response) objects of [`type`](../response/type) "`opaque`" if the [`fetchEvent.request`](request) object's [`mode`](../request/mode) is "`no-cors`". This prevents the leaking of private data.
-   You can only return [`Response`](../response) objects of [`type`](../response/type) "`opaqueredirect`" if the [`fetchEvent.request`](request) object's [`mode`](../request/mode) is "`manual`".
-   You cannot return [`Response`](../response) objects of [`type`](../response/type) "`cors`" if the [`fetchEvent.request`](request) object's [`mode`](../request/mode) is "`same-origin`".

### Specifying the final URL of a resource

From Firefox 59 onwards, when a service worker provides a [`Response`](../response) to [`FetchEvent.respondWith()`](respondwith), the [`Response.url`](../response/url) value will be propagated to the intercepted network request as the final resolved URL. If the [`Response.url`](../response/url) value is the empty string, then the [`FetchEvent.request.url`](../request/url) is used as the final URL.

In the past the [`FetchEvent.request.url`](../request/url) was used as the final URL in all cases. The provided [`Response.url`](../response/url) was effectively ignored.

This means, for example, if a service worker intercepts a stylesheet or worker script, then the provided [`Response.url`](../response/url) will be used to resolve any relative [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) or [`importScripts()`](../workerglobalscope/importscripts) subresource loads ([bug 1222008](https://bugzilla.mozilla.org/show_bug.cgi?id=1222008)).

For most types of network request this change has no impact because you can't observe the final URL. There are a few, though, where it does matter:

-   If a [`fetch()`](../windoworworkerglobalscope/fetch) is intercepted, then you can observe the final URL on the result's [`Response.url`](../response/url).
-   If a [worker](../web_workers_api) script is intercepted, then the final URL is used to set `self.location` and used as the base URL for relative URLs in the worker script.
-   If a stylesheet is intercepted, then the final URL is used as the base URL for resolving relative [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) loads.

Note that navigation requests for [`Windows`](../window) and [`iframes`](../htmliframeelement) do NOT use the final URL. The way the HTML specification handles redirects for navigations ends up using the request URL for the resulting [`Window.location`](../window/location). This means sites can still provide an "alternate" view of a web page when offline without changing the user-visible URL.

Syntax
------

    fetchEvent.respondWith(
      // Promise that resolves to a Response.
    );

### Parameters

A [`Response`](../response) or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a `Response`. Otherwise, a network error is returned to Fetch.

### Return value

`undefined`.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Notes</th></tr></thead><tbody><tr class="odd"><td><code>NetworkError</code></td><td>A network error is triggered on certain combinations of <a href="../request/mode"><code>FetchEvent.request.mode</code></a> and <a href="../response/type"><code>Response.type</code></a> values, as hinted at in the "global rules" listed above.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The event has not been dispatched or <code>respondWith()</code> has already been invoked.</td></tr></tbody></table>

Examples
--------

This fetch event tries to return a response from the cache API, falling back to the network otherwise.

    addEventListener('fetch', event => {
      // Prevent the default, and handle the request ourselves.
      event.respondWith(async function() {
        // Try to get the response from a cache.
        const cachedResponse = await caches.match(event.request);
        // Return it if we found one.
        if (cachedResponse) return cachedResponse;
        // If we didn't find a match in the cache, use the network.
        return fetch(event.request);
      }());
    });

**Note**: [`caches.match()`](../cachestorage/match) is a convenience method. Equivalent functionality is to call [`cache.match()`](../cache/match) on each cache (in the order returned by [`caches.keys()`](../cachestorage/keys)) until a [`Response`](../response) is returned.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-respondwith">Service Workers<br />
<span class="small">The definition of 'respondWith()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`respondWith`

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

≤79

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

59

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)).

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

?

29

No

4.0

`resource_url`

No

No

59

No

?

No

No

No

?

?

No

No

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Fetch API](../fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/respondWith" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/respondWith</a>
