# CacheStorage.keys()

The ` keys``() ` method of the [`CacheStorage`](../cachestorage) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will resolve with an array containing strings corresponding to all of the named [`Cache`](../cache) objects tracked by the [`CacheStorage`](../cachestorage) object in the order they were created. Use this method to iterate over a list of all [`Cache`](../cache) objects.

You can access `CacheStorage` through the global [`caches`](../windoworworkerglobalscope/caches) property.

## Syntax

    caches.keys().then(function(keyList) {
      //do something with your keyList
    });

### Parameters

None.

### Return value

a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of the [`Cache`](../cache) names inside the [`CacheStorage`](../cachestorage) object.

## Examples

In this code snippet we wait for an [`activate`](../serviceworkerglobalscope/onactivate) event, and then run a [`waitUntil()`](../extendableevent/waituntil) block that clears up any old, unused caches before a new service worker is activated. Here we have a whitelist containing the names of the caches we want to keep (`cacheWhitelist`). We return the keys of the caches in the [`CacheStorage`](../cachestorage) object using `keys()`, then check each key to see if it is in the whitelist. If not, we delete it using [`CacheStorage.delete()`](delete).

    then.addEventListener('activate', function(event) {
      var cacheWhitelist = ['v2'];

      event.waitUntil(
        caches.keys().then(function(keyList) {
          return Promise.all(keyList.map(function(key) {
            if (cacheWhitelist.indexOf(key) === -1) {
              return caches.delete(key);
            }
          });
        })
      );
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-storage-keys">Service Workers<br />
<span class="small">The definition of 'CacheStorage: keys' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`keys`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/keys</a>
