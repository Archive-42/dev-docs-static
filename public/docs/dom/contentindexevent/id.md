# ContentIndexEvent.id

**Draft**

This page is not complete.

The read-only `id` property of the [`ContentIndexEvent`](../contentindexevent) interface is a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) which identifies the deleted content index via it's `id`.

## Syntax

    var id = ContentIndexEvent.id;

### Value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the deleted content index id.

## Examples

This example listens for the [`contentdelete`](../contentindexevent) event and logs the removed content index id.

The [`ContentIndexEvent`](../contentindexevent) is only available to the [`global scope`](../serviceworkerglobalscope) of a [`ServiceWorker`](../serviceworker).

    self.addEventListener('contentdelete', (event) => {
      console.log(event.id);

      // logs content index id, which can then be used to determine what content to delete from your cache

    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index-event">Content Index API<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.ContentIndexEvent.id`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
- [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)
- [Service Worker API, along with information about Cache and CacheStorage](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent/id</a>
