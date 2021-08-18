# ContentIndexEvent

**Draft**

This page is not complete.

The `ContentIndexEvent` interface of the [`Content Index API`](content_index_api) defines the object used to represent the `contentdelete` event.

This event is sent to the [`global scope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). It contains the id of the indexed content to be removed.

The `contentdelete` event is only fired when the deletion happens due to interaction with the browser's built-in user interface. It is not fired when the [`ContentIndex.delete`](contentindex/delete) method is called.

## Constructor

[`ContentIndexEvent()`](contentindexevent/contentindexevent)  
Creates and returns a new `ContentIndexEvent` object whose type and other options are configured as specified.

## Properties

_In addition to the properties listed below, this interface inherits the properties of its parent interface, [`ExtendableEvent`](extendableevent)._

[`id`](contentindexevent/id) <span class="badge inline readonly">Read only </span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) which identifies the deleted content index via it's `id`.

## Methods

_While `ContentIndexEvent` offers no methods of its own, it inherits any specified by its parent interface, [`ExtendableEvent`](extendableevent)._

## Examples

This example shows the [`sevice worker`](serviceworker) script listening for the [`contentdelete`](contentindexevent) event and logs the removed content index id.

    self.addEventListener('contentdelete', (event) => {
      console.log(event.id);

      // logs content index id, which can then be used to determine what content to delete from your cache

    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index-event">Content Index API<br />
<span class="small">The definition of 'ContentIndexEvent' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ContentIndexEvent`

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
- [Service Worker API, along with information about Cache and CacheStorage](service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndexEvent</a>
