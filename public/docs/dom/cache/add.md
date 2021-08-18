# Cache.add()

The `add()` method of the [`Cache`](../cache) interface takes a URL, retrieves it, and adds the resulting response object to the given cache. The `add()` method is functionally equivalent to the following:

    fetch(url).then(function(response) {
      if (!response.ok) {
        throw new TypeError('bad response status');
      }
      return cache.put(url, response);
    })

For more complex operations, you'll need to use [`Cache.put()`](put) directly.

**Note**: `add()` will overwrite any key/value pair previously stored in the cache that matches the request.

## Syntax

    cache.add(request).then(function() {
      // request has been added to the cache
    });

### Parameters

request  
The request you want to add to the cache. This can be a [`Request`](../request) object or a URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`.

### Exceptions

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th><strong>Exception</strong></th><th><strong>Happens when</strong></th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td><p>The URL scheme is not <code>http</code> or <code>https</code>.</p><p>The Response status is not in the 200 range (i.e., not a successful response.) This occurs if the request does not return successfully, but also if the request is a <em>cross-origin no-cors</em> request (in which case the reported status is always 0.)</p></td></tr></tbody></table>

## Examples

This code block waits for an [`InstallEvent`](../installevent) to fire, then calls [`waitUntil()`](../extendableevent/waituntil) to handle the install process for the app. This consists of calling [`CacheStorage.open`](../cachestorage/open) to create a new cache, then using [`Cache.add`](add) to add an asset to it.

    this.addEventListener('install', function(event) {
      event.waitUntil(
        caches.open('v1').then(function(cache) {
          return cache.add('/sw-test/index.html');
        })
      );
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-add">Service Workers<br />
<span class="small">The definition of 'Cache: add' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`add`

44

Requires HTTPS from version 46.

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

31

Requires HTTPS from version 33.

11

44

Requires HTTPS from version 46.

44

Requires HTTPS from version 46.

39

32

Requires HTTPS from version 33.

11

4.0

Requires HTTPS from Samsung Internet 5.0.

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/add</a>
