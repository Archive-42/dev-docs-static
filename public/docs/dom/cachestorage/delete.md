# CacheStorage.delete()

The ` delete``() ` method of the [`CacheStorage`](../cachestorage) interface finds the [`Cache`](../cache) object matching the `cacheName`, and if found, deletes the [`Cache`](../cache) object and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true`. If no [`Cache`](../cache) object is found, it resolves to `false`.

You can access `CacheStorage` through the global [`caches`](../windoworworkerglobalscope/caches) property.

## Syntax

    caches.delete(cacheName).then(function(boolean) {
      // your cache is now deleted
    });

### Parameters

`cacheName`  
The name of the cache you want to delete.

### Return value

a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if the [`Cache`](../cache) object is found and deleted, and `false` otherwise.

## Examples

In this code snippet we wait for an activate event, and then run a [`waitUntil()`](../extendableevent/waituntil) block that clears up any old, unused caches before a new service worker is activated. Here we have an array of cache names we want to keep (`cachesToKeep`). We return the keys of the caches in the [`CacheStorage`](../cachestorage) object using [`CacheStorage.keys`](keys), then check each key to see if it is in the array. If not, we delete it using `delete()`.

    this.addEventListener('activate', function(event) {
      var cachesToKeep = ['v2'];

      event.waitUntil(
        caches.keys().then(function(keyList) {
          return Promise.all(keyList.map(function(key) {
            if (cachesToKeep.indexOf(key) === -1) {
              return caches.delete(key);
            }
          }));
        })
      );
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-storage-delete">Service Workers<br />
<span class="small">The definition of 'CacheStorage: delete' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`delete`

40

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

Yes

4.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WindowOrWorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/delete</a>
