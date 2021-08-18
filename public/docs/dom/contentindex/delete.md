# ContentIndex.delete()

**Draft**

This page is not complete.

The `delete()` method of the [`ContentIndex`](../contentindex) interface unregisters an item from the currently indexed content.

Calling `delete()` only affects the index. It does not delete anything from the [`Cache`](../cache).

## Syntax

    ContentIndex.delete(id).then(...);

### Parameters

This method receives no parameters.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`

### Exceptions

No exceptions are thrown.

## Examples

Below is an asynchronous function, that removes an item from the <span class="page-not-created">`content index`</span>. We receive a reference to the current [`ServiceWorkerRegistration`](../serviceworkerregistration), which allows us to access the [`index`](../serviceworkerregistration/index) property and thus access the `delete` method.

    async function unregisterContent(article) {

      // reference registration
      const registration = await navigator.serviceWorker.ready;

      // feature detect Content Index
      if (!registration.index)
        return;

      // unregister content from index
      await registration.index.delete(article.id);
    }

The `delete` method can also be used within the [`service worker`](../serviceworker) scope.

    self.registration.index.delete('my-id');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index-delete">Content Index API<br />
<span class="small">The definition of 'delete' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

No

No

No

No

No

No

84

84

No

60

No

14.0

## See also

- [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
- [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)
- [Service Worker API, along with information about Cache and CacheStorage](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/delete</a>
