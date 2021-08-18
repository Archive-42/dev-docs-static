ServiceWorkerGlobalScope.oncontentdelete
========================================

**Draft**

This page is not complete.

The `oncontentdelete` property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is an event handler fired when an item is removed from the indexed content via the user agent.

Syntax
------

    ServiceWorkerGlobalScope.oncontentdelete = function(event) { ... };

Examples
--------

The following example uses a `contentdelete` event handler to remove cached content related to the deleted index item.

    self.addEventListener('contentdelete', event => {
      event.waitUntil(
        caches.open('cache-name').then(cache => {
          return Promise.all([
            cache.delete(`/icon/${event.id}`),
            cache.delete(`/content/${event.id}`)
          ])
        })
      );
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#extensions-to-service-worker-global">Content Index API<br />
<span class="small">The definition of 'contentdelete' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.ServiceWorkerGlobalScope.contentdelete`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Content Index API`](../content_index_api)
-   [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
-   [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/oncontentdelete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/oncontentdelete</a>
