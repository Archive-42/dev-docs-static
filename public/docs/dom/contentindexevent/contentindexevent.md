# ContentIndexEvent()

**Draft**

This page is not complete.

The `ContentIndexEvent()` constructor creates a new [`ContentIndexEvent`](../contentindexevent) object whose type and other options are configured as specified.

## Syntax

    var ContentIndexEvent = new ContentIndexEvent(type, ContentIndexEventInit);

### Parameters

_type_  
A [`DOMString`](../domstring) indicating the event which occurred. For `ContentIndexEvent`, this is always `delete`.

_eventInitDict_ <span class="badge inline optional">Optional</span>  
An options object containing any initialization data you want to populate the `ContentIndexEvent` object with. The options are:

- `id`: The id of the indexed content you want the `ContentIndexEvent` to remove.

### Return value

A [`ContentIndexEvent`](../contentindexevent) object configured using the given inputs.

## Examples

This examples constructs a new [`ContentIndexEvent`](../contentindexevent) with the relevant id.

    var removeData = {
      id : 'unique-content-id'
    }

    var ciEvent = new ContentIndexEvent('contentdelete', removeData);

    ciEvent.id; // should return 'unique-content-id'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index-event">Content Index API<br />
<span class="small">The definition of 'ContentIndexEvent' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.ContentIndexEvent.ContentIndexEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
- [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)
- [Service Worker API, along with information about Cache and CacheStorage](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent/ContentIndexEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent/ContentIndexEvent</a>
