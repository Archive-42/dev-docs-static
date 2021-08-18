# Request.cache

The `cache` read-only property of the [`Request`](../request) interface contains the cache mode of the request. It controls how the request will interact with the browser's [HTTP cache](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching).

## Syntax

    var currentCacheMode = request.cache;

### Value

A `RequestCache` value. The available values are:

- `default` — The browser looks for a matching request in its HTTP cache.
  - If there is a match and it is [fresh](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching#freshness), it will be returned from the cache.
  - If there is a match but it is stale, the browser will make a [conditional request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Conditional_requests) to the remote server. If the server indicates that the resource has not changed, it will be returned from the cache. Otherwise the resource will be downloaded from the server and the cache will be updated.
  - If there is no match, the browser will make a normal request, and will update the cache with the downloaded resource.
- `no-store` — The browser fetches the resource from the remote server without first looking in the cache, _and will not_ update the cache with the downloaded resource.
- `reload` — The browser fetches the resource from the remote server without first looking in the cache, _but then will_ update the cache with the downloaded resource.
- `no-cache` — The browser looks for a matching request in its HTTP cache.
  - If there is a match, _fresh or stale,_ the browser will make a [conditional request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Conditional_requests) to the remote server. If the server indicates that the resource has not changed, it will be returned from the cache. Otherwise the resource will be downloaded from the server and the cache will be updated.
  - If there is no match, the browser will make a normal request, and will update the cache with the downloaded resource.
- `force-cache` — The browser looks for a matching request in its HTTP cache.
  - If there is a match, _fresh or stale_, it will be returned from the cache.
  - If there is no match, the browser will make a normal request, and will update the cache with the downloaded resource.
- `only-if-cached` — The browser looks for a matching request in its HTTP cache.

  - If there is a match, _fresh or stale_, it will be returned from the cache.
  - If there is no match, the browser will respond with a [504 Gateway timeout](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/504) status.

  The `"only-if-cached"` mode can only be used if the request's `mode` is `"same-origin"`. Cached redirects will be followed if the request's `redirect` property is `"follow"` and the redirects do not violate the `"same-origin"` mode.

## Example

    // Download a resource with cache busting, to bypass the cache
    // completely.
    fetch("some.json", {cache: "no-store"})
      .then(function(response) { /* consume the response */ });

    // Download a resource with cache busting, but update the HTTP
    // cache with the downloaded resource.
    fetch("some.json", {cache: "reload"})
      .then(function(response) { /* consume the response */ });

    // Download a resource with cache busting when dealing with a
    // properly configured server that will send the correct ETag
    // and Date headers and properly handle If-Modified-Since and
    // If-None-Match request headers, therefore we can rely on the
    // validation to guarantee a fresh response.
    fetch("some.json", {cache: "no-cache"})
      .then(function(response) { /* consume the response */ });

    // Download a resource with economics in mind!  Prefer a cached
    // albeit stale response to conserve as much bandwidth as possible.
    fetch("some.json", {cache: "force-cache"})
      .then(function(response) { /* consume the response */ });

    // Naive stale-while-revalidate client-level implementation.
    // Prefer a cached albeit stale response; but update if it's too old.
    // AbortController and signal to allow better memory cleaning.
    // In reality; this would be a function that takes a path and a
    // reference to the controller since it would need to change the value
    let controller = new AbortController();
    fetch("some.json", {cache: "only-if-cached", mode: "same-origin", signal: controller.signal})
      .catch(e => e instanceof TypeError && e.message === "Failed to fetch" ?
        ({status: 504}) : // Workaround for chrome; which fails with a typeerror
        Promise.reject(e))
      .then(res => {
        if (res.status === 504) {
          controller.abort()
          controller = new AbortController();
          return fetch("some.json", {cache: "force-cache", mode: "same-origin", signal: controller.signal})
        }
        const date = res.headers.get("date"), dt = date ? new Date(date).getTime() : 0
        if (dt < (Date.now() - 86400000)) {
          // if older than 24 hours
          controller.abort()
          controller = new AbortController();
          return fetch("some.json", {cache: "reload", mode: "same-origin", signal: controller.signal})
        }

        // Other possible conditions
        if (dt < (Date.now() - 300000)) // If it's older than 5 minutes
          fetch("some.json", {cache: "no-cache", mode: "same-origin"}) // no cancellation or return value.
        return res
      })
      .then(function(response) { /* consume the (possibly stale) response */ })
      .catch(error => { /* Can be an AbortError/DOMError or a TypeError */ });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-cache">Fetch<br />
<span class="small">The definition of 'cache' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`cache`

64

14

48

No

51

10.1

64

64

No

47

10.3

9.0

`only_if_cached`

No

No

50

No

No

No

No

No

No

No

No

No

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/cache" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/cache</a>
