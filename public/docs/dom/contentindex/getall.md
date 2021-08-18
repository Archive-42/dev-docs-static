# ContentIndex.getAll()

**Draft**

This page is not complete.

The `getAll()` method of the [`ContentIndex`](../contentindex) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an iterable list of content index entries.

## Syntax

    var indexedContent = ContentIndex.getAll();

### Parameters

This method receives no parameters.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of `ContentDescription` items.

_ContentDescription_  
Each item returned is an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) containing the following data:

- `id`: A unique [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) identifier.
- `title`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) title for the item. Used in user-visible lists of content.
- `title`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) title of the item. Used in user-visible lists of content.
- `description`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) description of the item. Used in user-visible lists of content.
- `url`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the url of the corresponding HTML document. Needs to be under the scope of the current [`service worker`](../serviceworker).
- `category`: <span class="badge inline optional">Optional</span> A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) defining the category of content. Can be:
  - `''` An empty [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), this is the default.
  - `homepage`
  - `article`
  - `video`
  - `audio`
- `icons`: <span class="badge inline optional">Optional</span> An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of image resources, defined as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the following data:
  - `src:` A url [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) of the source image.
  - `sizes:` <span class="badge inline optional">Optional</span> A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the image size.
  - `type:` <span class="badge inline optional">Optional</span> The [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the image.

### Exceptions

No exceptions are thrown. If there are no items in the Content Index, an empty [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) is returned.

## Examples

The below example shows an asynchronous function that retrieves items within the [`content index`](../content_index_api) and iterates over each entry, building a list for the interface.

    async function createReadingList() {
      // access our service worker registration
      const registration = await navigator.serviceWorker.ready;

      // get our index entries
      const entries = await registration.index.getAll();

      // create a containing element
      const readingListElem = document.createElement('div');

      // test for entries
      if (!Array.length) {

        // if there are no entries, display a message
        const message = document.createElement('p');
        message.innerText = 'You currently have no articles saved for offline reading.'

        readingListElem.append(message);

      } else {

        // if entries are present, display in a list of links to the content
        const listElem = document.createElement('ul');

        for (const entry of entries) {
          const listItem = document.createElement('li');

          const anchorElem = document.createElement('a');
          anchorElem.innerText = entry.title;
          anchorElem.setAttribute('href', entry.url);

          listElem.append(listItem);

        }

        readingListElem.append(listElem);
      }

    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#dom-contentindex-getall">Content Index API<br />
<span class="small">The definition of 'getAll' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/getAll</a>
